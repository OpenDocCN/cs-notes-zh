# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p159 18_16_overriding-and-dynamic-dispatch -BV1bw4m1D7MM_p159-

In this segment I want to continue our study of subclassing with two classes that override methods of the superclass in interesting ways。

 in particular the second one will be much more interesting because it will use the key idea of dynamic dispatch。

 which is at the heart of object oriented programming。



![](img/a09ad5db32ed4abbe77998ac94ced1ac_1.png)

So let me show you the code we'll do most of it that way。

 here is this class point that we're familiar with and have been using。

 remember it has getters and setters for x and y and has two different ways of computing the distance from the origin。

 the first way just directly accesses instanceense variables X and Y。

 the second way uses the object's own getter methods by calling self。 X and self。

t Y with nll arguments。So that's a point class。 Now let's consider a rather controversial subclass。

 I'll explain why in just a second， which are three dimensional points。

 So in this subclass we in addition to having an x coordinate and a Y coordinate have a Z coordinate。

 which is for the height to a point in three dimensional space。

 So I just add getter methods for Z and set methods as well。

 and then I change via overriding the initialized method to actually require three arguments。

I use super here so that the initialized method in the point class can be used to initialize x and y。

 and then I set at z equal to the z argument so now I also need to override disk from origin and disk from origin2 these need to do different things for a three dimensionmensal point it turns out the distance from the origin in three dimensionmenal space is a square root of x squared plus y squared plus z squared I could implement those directly and maybe I could do that would be even shorter here but I decided to show super in a similar way so for distance from origin I could get the distance in terms of the x and y coordinate by calling super here that will call the disk from origin method in the super class let that be in this local variable D and then take the square root of d times d plus at z times at z and that would get me the proper distance for disk from origin2 I continue this approach of using as helper methods。

 my own getter methods and so I end up。with a similar thing。

 except I call disform origin2 in the superclass， and then add to that the result of calling the Z。

 calling the Z method， multiplying them together， and then I take the square root。

So why is this controversial， Oh， people have been arguing about this for decades。

 You could certainly make an argument that it's a hack。

 It's an abuse of subclassing to treat three dimensionmenal points as points。

 because they really are a different thing。 It's not clear that a point in three dimensionmensal space is a point in twodisal space。

 They're kind of fundamentally different things。 whereas other people argue， no， no， no。

 that makes perfect sense。 First of all， you get lots of code reuse。 and we like code reuse。

 And moreover， you can think of it as a two dimensionmensal point。

 Maybe it's the projection of the point down onto the X Y plane。

 It's the equivalent of treating the Z coordinate as zero。

Other people would argue that if that's how you feel about it。

 that's not how these disform origin methods behave。

 they do not return the distance from the origin of that projected point。

 they return it in three dimensionsal space and you can argue about this all day long。

I just want to argue here that even if this is poor style。

 it does help us learn the semantics of overriding， that when I create an instance of 3D point。

 I inherit the methods X x equal y and y equal， I override the methods initialize disform origin。

 disform origin 2， and I add the methods Z and z equal。

 and that is the definition of the methods defined for a 3D point。

 so it's a good example of how overriding occurs。😡。



![](img/a09ad5db32ed4abbe77998ac94ced1ac_3.png)

In fact， I want to argue that it's a fairly simple example。😡，Because with the examples so far。

 an object， like an instance of 3D point， is really not that different than a function closure。

A function closure just has one method call me， whereas a 3D point has， I don't know。

8 or9 methods disked from origin 2， Z equals and so on。Fine。😊。

The object has explicit instance variables at X， at Y， at Z。

 whereas a closure has all those things in the environment that it's allowed to use as its sort of private state。

 F， that's a moderate difference。We have this inheritance which let us inherit things from the superclass。

 but that's， as I've shown it so far， really just a code reuse convenience。

But there's a huge difference between subclassing and closures like in functional languages。

 which is what I'm about to show you， and that is there are ways to use overriding that can make a method you inherit from the superclass still call different methods in the subclass and this is the thing that object oriented programming does differently than non- objectject oriented languages。

 and so I want to emphasize that point。

![](img/a09ad5db32ed4abbe77998ac94ced1ac_5.png)

And I will do that pardon the pun， emphasize that point， sorry with this final class polar point。

 So if you remember your high school geometry， if not bear with me。

 a polar point is not represented by an x coordinate， a Y coordinate it's represented by a radius。

 a distance from the origin R and a theta， the angle of the point from flat。

 So you represent with an R and a theta。So here I am having polar point， subclass point。

 but I'm going to override a bunch。😡，I'm going to override just about everything， actually。

I'm going to have an initialized method that instead of taking an X and a Y takes an R and a theta and initializes different instance variables at R and at theta。

 Now， this is actually interesting。 My instances of polar point won't even have instance variables X and Y in most object RNA programming languages。

 it would have them but not use them。Here， because of how Ruby does instance variables。

 it doesn't even have them。 I'm just using different instance variables in my subclass。

So it turns out that I need to override X Y x equal and y equal because I need to compute those methods differently when my internal representation uses an r and a theta instead of an x and a y and the trigonometry is that the way you compute the value of the x coordinate is you return the radius times the cosine of the angle。

 So here is r times cosine theta and the y is r times sine of theta。 don't worry。

 you won't be tested on the trigonometry just pointing out that to the client。

 these look like getter methods， but they're actually performing an interesting computation。

Setter methods are actually a little more complicated if you want to set the x value in terms of some new x value。

 you still have the old y value and you have to do a bunch of stuff with arc tangent and square root and all sorts of stuff。

 I do believe this works， I'm just using this built in y getter method so I'm calling this method here。

 I'm storing it a local variable so I don't call y more than once。

 even though I use B multiple times and trust me that the math is correct。Y equals is similar。

 we do basically the same computation to set the new y field。Now for the interesting stuff。

Let's override disk from origin and disk from origin 2。 Well。

 it turns out the entire advantage of of a polar representation of a point is the disk from origin is trivial。

 That's exactly what the R instance variable holds。 So we need to do this override。

 If you look up in the super class。 This computation， sorry， that's 3D point。

 This computation would be wrong。 We would go to read the at X field or the at y field。

 They're not even there。 We would get nil back。 If you try to multiply nil， you get an error message。

 So it's essential that we do this override。But now。

 the fascinating part is that disk from origin2 doesn't need overr。 We could overwrite if we want。

 but it works as is。 And this is the thing I want to emphasize to you。

 If you look at disk from origin 2， what it does when called is called self dot X and self dot Y and then compute with the result。

Even though disc from origin 2 is inherited from the point class。

It is now down here part of the polar point class， and so when we execute those calls to self dot X and self dot Y on an instance of polar point。

😡，We get this code and this code， these methods。And therefore， this will work。 Let me prove that to。

 This is the key example。 I've already loaded the file。

 I could make a polarpoint new for comma how about math pi over4， So like this。

 and it turns out I could ask PP do X and you get 2。82 and you could ask P y and I get 2。82。

 So what's happening here in the code is even though there's an instance variable at R and an instance variable at theta when I call the x method or the y method。

 I do these computations， And it turns out I get 2。8 for both of them。If I ask PP。D from origin。

I get four， and that's because at R is 4， and this code right here just returns it。

 it really is just a getter for R。And now the interesting one， if I do disk for origin 2， I do get4。

 although it did some floating point computation， so I actually get 4。0。

 and that is because I inherit disk from origin 2， so I evaluate this code。

But in an environment where the object itself is an instance of polar point。

 so when I say self dot x and self do y， I execute this code down here。

 so I end up taking our cosine theta， our sine of theta， squaring them， taking the square root。

 and I get the right answer。😡。

![](img/a09ad5db32ed4abbe77998ac94ced1ac_7.png)

So。This is the key punchline。😡，That when you have a method。😡。

That makes another call on the same object when it uses self。That self is the entire object。

 and if self is an instance of the subclass， then you use the subclasss methods like the overridden X and y that we saw on our definition of polarPo。

 that is the thing that distinguishes object oriented programming and subclassing from other things we've seen in this course。

 so I've now shown you an example， and then an X segment we can take a step back and give a more precise definition of the semantics of method lookup so that we can understand this behavior precisely。



![](img/a09ad5db32ed4abbe77998ac94ced1ac_9.png)