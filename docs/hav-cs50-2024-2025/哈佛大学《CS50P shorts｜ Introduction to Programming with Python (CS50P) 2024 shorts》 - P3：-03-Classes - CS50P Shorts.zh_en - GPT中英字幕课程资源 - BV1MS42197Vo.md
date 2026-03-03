# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P3：-03-Classes - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

Well hello one and all and welcome to our short on classes we'll see here why we should create classes and the syntax we can use to do so Now I have here a program are called packages dotpi。

 whose goal is to really track packages we're sending between different users that we have I have here a list called packages and notice how it has two packages representatives strings inside of it。

 I have one package one Alice to Bob 10 kilogram and another one package two Bob Charlie5 kgram。

 so two different packages here inside of my list。Now there are a few different reasons you probably don't want to be using strings to represent these packages here now one of them is strings are flexible but arguably too flexible。

 I could very easily change the ordering that I have for each of these pieces of information about a package here I did follow this same pattern of maybe package number colon sender and then recipient comma weight。

 but I could very easily stray from that as I add more and more packages。

 I might want something it' a little more rigid can store information in a better way so thankfully I do have my disposal this thing called a class now a class operates a bit like a template that I can use to create various objects in my code I could think of each of these packages as being some object in fact I could literally look in the real world and see a package as some object。

I could think of my class as being a template to later create some object that looks a lot like a package but a particular package so here I have some pieces of information about this package I probably want to encapsulate to put inside my template one might be the ID of the package is it one。

 two， three some unique ID to refer to it later on I might also want to store the sender of the package as well as the recipient alongside of the weight as well so classes these templates allow me to encapsulate this information in a single place and not worry about all these different formatting that I have to maintain consistently in my code if I were to use something like a string for instance。

So to create a class to this template for a package I could literally type class just like this followed by the name from my class in this case package and by convention these class names tend to begin with uppercase so here we have capital P package and I could later on fill in this package but here I'm getting started on creating this template for some package that I can then use later on to create particular packages so let's think out what a template for a package might ideally store well to do so I need to first create this particular method one called Dunder in it which allows me to use my template my class here to later on instantiate or create some particular object from this template from this class so here I'll define in this case D in its these double underscores here and。

Turns out that this by convention must take at least one argument， one called self。

 When I create later on， a new object， this self refers to the instance that new object I'm creating when I work for instance to call something like package。

 we'll see that later on。The other thing this really wants to probably take as input here is all of the pieces of information I need to create some new package we' said down below we want to encapsulate or really combine a few different pieces of information。

 one is the package ID， one is the sender， and one is the recipient and one is the weight of the package here。

 so I could go ahead and say as input to this particular template that I have here。

 creating some new object later on， I'll go ahead and say each package has a number or some ID。

 it also has a sender， a recipient in this case a weight and this is my Dunder init method allows me in this case specify what information I'm encapsulating as part of this template。

 in this case all packages have some number， some sender， some recipient and some weight。

Well now we might see where self comes in within this Dunder init method。

 I could actually go ahead and try to assign to this new instance of my object。

 if everything I've passed in down below， I could say self do number equals number。

 self dot sender equals sender， self dot recipient equals recipient and self dot weight equals weight。

Now， this might be a little bit confusing at first。

 especially seeing self and especially having made up some of these actual pieces of information down below。

 but let's see what it could do for us and maybe walk through what's happening each step along the way。

So I ideally I want to rewrite my code on line10 here。

 this is not what I should be doing to represent packages。

 but I do now have this template that I'm able to use to instantiate to create various objects in this case individual packages Well down below here let's try doing just that I'll remove these strings and I'll then go ahead and as input to my list will I'll create some new package and I can do so in this case by typing my class name package followed by parentheses and now here is where I can actually use those arguments I gave to D in it when I use package parentheses I'm actually at least on one step of the way calling D in it to create for myself some new instance of this template。

What we said here that this should take beyond self， number， sender， recipient。

 and weight as arguments， so I can do this， I could say my first package's number is one。

And it's the sender， the sender is Alice， the recipient in this case is Bob and the weight the weight in this case will be 10。

 and so this is the way we've now defined some new instance of this particular class。

 a given package that has a number one the sender Alice。

 recipient Bob and the weight 10 for 10 heograms， let's go ahead and add in another package and their instance of this class。

 I could type package again， and I'll say number equals to sender equals Bob maybe recipient here was Charlie as before and the weight the weight of this package was five and so this is this is here our way of representing that second package in our list。

And now we have a much more methodical way of storing or encapsulating this information thanks to the class we've created above。

😊，But now let's see what this was doing here， we said self。 numberumber， self。ender， self。recipient。

 self。weight， well later on we'll actually see if we can access these things called instance variables。

 but we'll see that in another short This then was our short on classes。

 how to create them and the syntax is do so we'll see you next time。



![](img/b119aa71b33c2eef419c37dc35cbdf16_1.png)

![](img/b119aa71b33c2eef419c37dc35cbdf16_2.png)