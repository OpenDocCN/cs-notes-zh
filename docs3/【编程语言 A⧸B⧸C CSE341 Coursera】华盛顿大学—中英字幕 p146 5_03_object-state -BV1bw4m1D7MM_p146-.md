# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p146 5_03_object-state -BV1bw4m1D7MM_p146-

I want to continue studying objects and class definitions by showing you how objects can have their own state。

So the thing about an object state is that the state starts when you create the object。

 every time you call the method， you can use the state， you can change the state。

 you can add to the state， it persists across the entire object's lifetime。

Now that state is only accessible by calling methods on the object， it's private to the object。

 only methods of the object can access that state。So with that background understanding。

 let's get to the details about how you actually read and write the state。

The state is just a collection of variables， which we will call instance variables in which a lot of object oriented programming languages call fields。

 so if you've seen Java or CSR or C++ we're talking about fields here。

And all you do to create a field is assign to a variable that starts with the at character。

 So if some method of an object says at fo equals 34， then that object at fo instance variable is 34。

 And later in that method or in a later call to a different method on the same object。

 we can read at fo and we'll get 34。 So we just assign to something and it springs into being。

 So we didn't have to say what the instance variables are。

 and you have to be careful here because if you meant at food and you say at food or something else。

 you're just talking about a different instance variable。

 You can have as many as you want and they just come into existence as soon as you use them。😊。

In fact， if you use one that has never been assigned to for that object。

 then you would think you would get an error， accessing an undefined instance variable。

 but instead you get a special object in Ruby called the Nil object。

 which is vaguely similar to things like null in other languages。

 but is actually an object and we'll have more to say about that in the future。

Now that we have different objects that have different mutable state。

 we have to be curious about aliasing soon as you have mutation。

 aliasing matters in any programming language。 So let me tell you the aliasing story in Ruby。

 when you create an object by using new。 you get back a new object that is distinct from all previous objects and has different state than all of them。

 It's not alias to any of them， and it has no initial state until we get to something I'll show you in a couple minutes。

When you assign one variable to another like x equal y， that does create an alias。

 and the reason y is this。Y holds a reference to some object。 And so when you say x equal y。

 they now both hold references to the same object。 so they can both call methods on that object。

 and whatever private state of the object。 one method sets or changes will be seen by any other method on that object and x and y both refer to the same object in In other words。

 they alias。 So let's define a class to see all this in action。 again。

 we're just playing around with silly code here。 I'll show you a real example。

 something that does something useful in a segment or two。 So here's a class A。

 let's give it a M1 method that when you call it assigns to the instance variable， the value 0。

 So what this will do is if the object already has an at fu。 it will change it to0。 otherwise。

 it will add one and initialize it to 0。

![](img/3d6b6cac90ba376ed02a0f7a5b4dbe94_1.png)

M2， let's have it take some argument X and let's add to F whatever was already there plus X。

 And like in many programming languages， there's a little bit of syntactic sugar for this。

 We can write plus equal X， and that does the same thing。

And let's have a third method where the name of the method is fo。And when you evaluate it。

 it evaluates the expression， look up the instance variable fo and return it because it's the last thing in the method and methods return their last thing。

 And how about we just start with that simple class there and let's go over here。

 I already have the IRB open and let's load in the file。There we are。

 and now let's just play around with those three methods in our one class A。

So if I said something like x equal a dot nu。And then I said y equal a dot new。

 And then I said Z equal x based on our discussion of aliasing X and Y refer to different objects。

 X and Z refer to the same object。 And we can see that by calling some methods。 If I call x dot P。

I'm going to get back nil。 And The reason why is， when I call the fo method， it reads at fo。

 which has never been written to yet。 So it's not part of the object state yet。

 And so we get back nil。If on the other hand， I called X dot M2 with3， I actually get an error。

 And the reason is here I read adfo， which has never been assigned to on this object， get nil。

 and you can't call plus on nil。 So that's why we got the actual error message。

 Let's go ahead and fix that。 If I call X do M1。That will inside the object。

 set the instance variable food to be 0。Alright， and now remember that x and Z are aliases。

 So now if I call Z dot fo， I actually get back 0， not nil， like I would have before。

 But if I call Y dot fo， I still get nil because that object's instance variable has never been assigned to。

Okay，And we could do various things here now that we've done this if we called Z dot M2 on 17 and then called x dot M2 on 14。

 and then called Z dot， we would get 31。 Of course， once I call x dot M1。

 that's gonna set fo back to 0。 And so now if I called Z dot fo。 I get 0。

 So we really are updating state here。 Y is still over here with a nil。 But if I called y dot M1。

 and then y dot M2 with 7。 and then y dot I would get 7。 So that's the idea of instance variables。

 And now let's extend them a little bit。 So， first of all， of course， you could have more than1。

 maybe M2 would also make an add bar that would equal 0。😊。

But what I want to do now is tell you about a special method method that has a special status in Ruby。

 and that's a method called initialize。 So it acts like any other method。

 but it is called when you create objects。 So let's have this method initialize， Take one argument F。

 and go ahead and initialize P to be F。 This is much better style so that we don't have to worry about M2 causing errors or fo returning nil will always have an initialized。

 In fact， you can make any method in Ruby， Take a default argument so that if the caller doesn't pass an argument。

 it'll just default to0。😊，So how does this actually work。

 it turns out that you almost never call initialize directly that let me reload this so we can see this。

 it turns out this is the warning there is referring to some file I haven't shown you yet。

 some contents of the file I haven't shown you yet， it turns out in Ruby that when you say a dot new。

If your class has an initialized method， it will be called before the object returns。

So now if I said something like Q equals a dot nu。It turns out that Q already has a fo field and it's initialized to zero。

Similarly， if I called W with a dotnu and I pass some argument like 19。

 whatever arguments you pass to new get passed along to initialize。

 and since initialize can take one argument， we now have an object whose fo is 19 and after I called M2 on 7。

 I could ask W fo and I would get 26。So in general。

 it's just like any other method but new passes the arguments along and it gets called before new returns。

 any method has this issue where you can provide default values which allows the caller to call the method with too few arguments and the rest get filled in as a default so that's initialization let me talk to you about that just a second here on the slide initialize is special because of how it's called it's excellent for creating object invariance。

😡。

![](img/3d6b6cac90ba376ed02a0f7a5b4dbe94_3.png)

So what's going on here is it's usually good style to create your instance variables in initialize。

 but this is just the convention in other programming languages it's very common to have to say what your instance variables are。

 sometimes it's even required to initialize them in a method like initialize。

 which in many programming languages is called a constructor。😡，But in Ruby。

 this is just a convention and in fact， even different instances of the same class could。

 although it's not usually good style， have different instance variables in their state。

So that's the idea of instance variables to help contrast them with something else。

 I want to show you a couple things about classes that I didn't show you before。

So it turns out there are also things called class variables and these are not separate for every object。

 They're shared by all the instances of a particular class。

 So different classes still have different class variables。

 but all the objects of one class share the class variable。 Stactically， we just use double at。

 So for example， double at fo or at at fo is a class variable。 These are frankly。

 not particularly useful， but you do see them every once in a while。

 and I'm just showing them to you here because they contrast the idea with you of private state for objects that instance variables are separate for every object and these are not。

And as long as we're discussing classes， there's two other things that classes can have。

 The first is there are class constants。 These are things just defined in the class that start with the capital letter。

 you should not mutate them， I think in the current version of Ruby you get a warning but don't ever mutate them and these are just variables that can be used anywhere in the class or outside of the class they are actually public whereas class variables and instance variables are private。

 I'll talk about that more I think in the next segment and outside of class C。

 if there were a class constant fo you could write C colon and colon food to get it。

And there's also a notion of a class method， something that in Java is called a static method。

And the syndax for defining a class method is you just write self dot before the rest of the method name and I'm not going to explain here why。

 and then to use a class method， you don't write some object and then the method name and the arguments。

 you write the name of the class and then the method name in the arguments。

 you might guess that what's actually going on here is the class itself is also an object。

 but let's not think of it that way right here， and class methods are just things that cannot access any instance variables of an instance of the class because they're separate from any object。

 they sort of explicitly say I'm not part of a particular object of class C。

 I'm just kind of a helper function that can use the class constants in class variables but not anything from a particular object of class C。



![](img/3d6b6cac90ba376ed02a0f7a5b4dbe94_5.png)

So if we go back over here in the code， I have an example here of a class C that uses all these features。

 So here's a class variable thans age。 Here is a class method that when you call it sets the class variable bar。

 you can see with double add here to0。 and then it's kind of like my previous example。

 except now I have a my M2 method increments the class variable bar。

 in addition to what it used to do。 and I have a new helper method here bar that just returns the contents of the class variable。

 The one thing I wanted to show you is just that these class variables are really shared。

 So if I make two。Instances of C。 And let me just go ahead and reset the bar class variable。

Then if I say C1 do M1 of 7。Sorry， M2， there is no M1 method。 and then C2 dot M29。

 And then I say C 2 dot bar。It turns out to get back2。

 which means that the bar field has been incremented twice。

 And that's because it's shared by the two objects。 The objects are not alias。

 but they refer to the same class variable。 On the other hand， they have very different food fields。

 C ones fo field is 7。 and C2's fo field is 9。 And that's our introduction to instance variables。

 which are the state of objects， as well as a number of things that are shared by all instances of a class。



![](img/3d6b6cac90ba376ed02a0f7a5b4dbe94_7.png)