# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p168 27_06_multiple-inheritance -BV1bw4m1D7MM_p168-

We're now going to study a couple OOP concepts that you don't need for your homework assignment。

 but are important concepts and we could ask on the exam and are just worth knowing about。

 and in this segment we'll discuss multiple inheritance。So we've seen the basics。

 we've seen inheritance。 We've seen overriding。 We've seen dynamic dispatch。 Now。

 let's think about what it be useful and what would it mean for a class to have more than one super class。

 So over the next couple segments， we're going to see multiple inheritance。

 which is where you have exactly that and we'll see that it's useful but has some problems。

 C plus plus is the most wellknown language that does support multiple inheritance。

 Then we'll study ruby style mixins， which are less powerful， but have fewer of the problems。

 and then we'll study interfaces like you see in Java or C sharp that are even less powerful and have even fewer problems。

 So you get kind of a range in these things are different from each other and make sense in different settings。

 So here it's just multiple inheritance for now。 So the idea is if having super classes where you can inherit methods and override them is so useful。

 Then why limit yourself to just one。And what we'll see a little bit in this segment is that there are some awkward semantic issues about what things should mean and how multiple inheritance should work。

There are some other things I won't discuss， but may as well mention that it does make static type checking more complicated and it also makes implementing OOP languages efficiently more difficult。

 but we will focus here on just a couple of the semantics questions。

 but before we do that let's just make sure that multiple inheritance is something we might actually want it was actually useful and I think it is fair to say that there are situations where it is useful。

 Now how many that's a matter of what kind of software you're writing。

 but let's just look at some code here， like I have here in this ruby file。

 it's a small example so I can go through it in just a minute or so。

 but suppose I have a class point。

![](img/0f420c7e5cb52bc35d3bbf767f6c39be_1.png)

That has getters and setters for X and Y， the X coordinate。

 the y coordinate and a little method for the distance to the origin。 And as we've seen before。

 a very natural subclass for this would be a class color point that maybe adds a getter and setter for a color field and maybe even has some method that adds dark to the color。

 So if you call darken and the color is currently gray。 you get dark gray。 If you call it again。

 you get dark， dark gray and so on。We might also take this class point and subclass it with 3D point。

 as we discussed before， this is very controversial， but you can create a subclass。

That adds a getter and a setter for Z and overrides the distance to the origin method。

Especially if you spell it。Oh， I guess we spelled it incorrectly in both of them。

 but it doesn't matter。And finally， what if we now wanted a color 3D point？😡。

So in a language with multiple inheritance， you would just write something like this。

 You would just create a class color point 3D that， you know。

 had superclass color point and point 3D。 And， of course， you could add more stuff if you wanted。

 But in this case， actually， all we want to do is inherit all this stuff from color point and all this stuff from 3D point。

 But you can't do that in Ruby， there's just no syntax for it。

 you get exactly one superclass object if you don't indicate one。 So in Ruby。

 if you want color 3D points， you end up copying code and repeating things。

 There's kind of two natural ways to do it。 One way is that you could subclass color point and add the getter and setter for Z。

 and then override disk to origin。😊，The other possibility is that you subclass 3D point and add color and add the darkened method。

 and it's not clear to me which you would prefer， probably whichever one is shorter。

 but neither really captures the idea that which you want is to have everything from two different superclasses。



![](img/0f420c7e5cb52bc35d3bbf767f6c39be_3.png)

So there are other examples， for example， if you wanted a student athlete class。

 maybe you want to inherit from the student class and the athlete class that maybe both inherit from some common superclass like person。

 and then you would get all the attributes that a student has and that an athlete has and so on。

So before we go on， let me introduce just a little bit of terminology for how to think about this stuff。

 and the first thing I want to emphasize is when we talk about subclass and superclass。

 we can often confuse each other when we communicate。So sometimes we mean the immediate subclass。

 A is the immediate subclass of B， if a lists as its superclass B。

 and other times we mean transitive subclasses， which means that。It is a subclass。

 but it may be because of multiple superclass relationship。

 so if a is a subclass of B and B is a subclass of C， then a is a subclass of C。

 but it's not the immediate subclass， it's a transitive subclass fine。

So in a language with single inheritance， basically all of your subclass relationships form a tree。

 we actually call this tree the class hierarchy so you could represent， for example。

 maybe there are three classes that subclass A， B， C and D。

 and maybe another class E that subclass is D， so the idea is that your parent in the tree is your immediate superclass。

What multiple inheritance fundamentally does is make the class hierarchy not a tree anymore。

 Instead it's a directed acyclic graph。 It has situations where something can have multiple parents。

 if you will。 multiple parents in the class hierarchy and therefore there are multiple paths between as you see in this example here。

 the class Y in the class X。 Y is a transitive subclass of x， and there are two ways to show it。

 you can show it that Y is a subclass of v， which is a subclass of x or y is a subclass of Z。

 which is a subclass of W， which is a subclass of x。

 and that's where things start to get a little more awkward。For example。

 suppose V and Z both define a method M。Which one does why inherit？

That didn't really happen with our color 3D points。

 but if they define any differently or maybe they both override some method in x。

 which one does y get？Maybe why needs to override it。 What if why wants to use super， Well。

 now it has to say which super it means。 I'm not saying any of these problems can't be surmounted。

 but they make your language more sophisticated and more complicated。😡。

Here's another situation where it's not even clear if you should do the same thing as the previous point or something different。

 Suppose X at the top here defines a method M。 Z overrides it。 sorry， Z overrides it。 Yes。

 and V does not。Well， now what method M do we have in Y， Is somehow it important that Z overrides it。

 or does somehow Y get z's method M and x' is because V did inherit it。 V does have a method M。

 It probably should not matter to us that V inherited it rather than defined it itself。

 maybe from Y's perspective， All that matters is that V has the method M。And then fields。

 what Ruby calls instance variables， but in most object learning programming languages can be part of a class definition get even more complicated。

 supposeupp there's some instance variable defined up in X should Y have one copy of it which kind of make sense It's an object that has an instance variable or does it need two different ones and for that I thought I'd show you that actually both situations do arise in practice。

 that's why C+ plus which I'm not going to show you actually supports different kinds of subclassing and inheritance for this situation so its sometimes you get two different fields basically the same name just from different classes and sometimes you get only one。

So in our 3D color point example。It turns out that we have this situation where point has two subclasses。

 color point 03D， and then color point 3D， if we could do this would have two superclass。So。

It seems clear that in our 3D color points， we want to have one x getter，1 y getter，1 x setter。

1 y setter。 We want to have one conceptual field for the x coordinate， one for the Y coordinate。

 We don't want two coordinate systems，1 from color point，1 from point3D。 We want one。

 And that's an example where that's what you want。A short example where you actually want two different copies of the instance variable is a little sier。

 but I actually find it funny， so I will show this to you in this situation。

 we imagine at the top we have the class person。😊，And it has two subclasses， artists and cowboy。

 These are two different kinds of people。 artistsists draw things。 And Cowboys， well， now。

 if you don't know English， you may not realize this。 Cowboys also draw things。

 turnss out when you pull a gun out， it's called drawing the gun。

 So the same way an artist might draw a picture， A cowboy might draw a weapon。Now。

 there's nothing unreasonable about having an artist cowboy。

 This is someone who likes to paint pictures and be a cowboy and do all the things that cowboys do。

 But now it would have to draw methods。 And that makes sense because there this artist Carboy sometimes draws pictures and sometimes draws weapons。

But。😡，If both of those draw methods use the same instance variable。

 say pocket because the artist needs to draw a paintbrush out of his pocket and a cowboy needs to draw a gun out of his pocket。

 then for these methods to work correctly we actually want our artist cowboy to have two pocket getter methods to have two pocket fields。

 pocket instance variables and that somehow when we do this subclassing。

 we want to duplicate the idea of having a pocket and for an artist cowboy to essentially have an artist's pocket and have a cowboy pocket。

 and so there's no general solution to this， we wanted one semantics for 3D color points and a different semantics for artist cowboys and these sort of complications are why number of languages avoid these issues by choosing not to support multiple inheritance。



![](img/0f420c7e5cb52bc35d3bbf767f6c39be_5.png)