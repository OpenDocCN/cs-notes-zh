# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p149 8_06_everything-is-an-object -BV1bw4m1D7MM_p149-

I've said a few times now that in Ruby， everything is an object。

 And here I want to focus a little bit more on what I mean by that and show you some related idioms that work well in Ruby。

 So Ruby is fully committed to the fact that every result of every expression is a value。

 This leads to a smaller， more regular language。 than if you have some exceptions to that rule。

 like oh， except for numbers or oh， except for some special null value or something like that。

 And so as a result， you can call any method on any object。 Now。

 that object may not have that method defined in which case you just get an error that the method is undefined。

Actually， it's even a little more interesting than that。

 What actually happens is the Ruby interpreter， the Ruby implementation， says， oh。

 that object doesn't have that method， I will call its method missing method instead。

 and it turns out that the built- in method missing method that by default every class has defined prints out that error message。

We've also already seen things that like almost everything in Ruby is a method call。

 we've seen that when we call addition that's really just sending the plus message and things like that。

 so let me show that with numbers because they're a good example so I can you know of course write3 plus4 and get seven。

 I can also write three dot plus and then parentheses4 because that's just the version without syntactic sugar。



![](img/caec8dcbfb63bec2aef02199ccb04d46_1.png)

I could also say3 dot abs， which is the absolute value method I've shown you that before There's a method called non-zero that just returns the number itself unless you have the value0 and then of course you get nil and of course we don't have to do this on integer constants you know we could have a variable that hold something like if3 is greater than 4 then 5 L negative 5 n and you know x is minus5 and x dot abs is 5 and so on。

 All right， so that's kind of pure object oriented programming with numbers。

 the next thing I want to talk a little bit about is this value nil So nil is used in Ruby as sort of the object you used when you don't really have any data。

 So it's not unlike Mls unit or null in Java or C or C plus plus or C sharp， but it is an object。

 and that's the key difference。 So I could call。Nil with various methods now。

 doesn't have a lot of methods defined， but it does have a nil question mark method that it returns true for。

 Everything else returns false。You know， a string is not nil and so on， not even the empty string。

Okay， but nil is。Nil question mark。 Nil has a bunch of other methods as well。 I will point out。

 by the way， that in Ruby， the nil object counts as false。

 So there are two things in Ruby that are false。 The false constant and the nil object。 So indeed。

 if I said， you know， maybe y equals if 3 is greater than 4， which it's not the nil else42 N。

 So y sorry， the other way。How about4 greater than3。There we go。 Get true。 Now， y is Neil。 And now。

 if I said if y， then put S A else， put S。B。Then it did printed out B， because the nil object。

 anything that evaluates the nil counts as false。 So that's interesting。 and and so on and so forth。

 Everything is just method calls。 So now what I want to emphasize is that all the code in our program is just methods。

 Everything is a method of some class。 All right， and then you call that code by making an instance of the object and calling it on that class。

 So top levelvel methods， you might think are somehow different。 But it turns out they're not。

 if you put a top levelve method outside of any class definition in a file or in the repel。

 then it just gets added to the object class。 Now the object class is something that is a super class of all other classes。

 Now we haven't talked about subclassing yet， we'll study it explicitly a little bit later in this section。

 but what basically happens for the purpose of this discussion is when you define a class。

 you also get in your class， all the methods of all your super classes。



![](img/caec8dcbfb63bec2aef02199ccb04d46_3.png)

So since object is a superclass of all the classes you define。

 you get all of its methods as long as you don't replace them with a method of the same name。

 So those top levell methods are now just methods of every object because they're in every class。

 So again， it's just object oriented programming。 It's just a way of thinking about top levelvel methods that is more OOP style and fits into the sort of the small ruby language。

So the last thing I want to emphasize in this segment is that this thing called reflection and how it can be used for exploratory programming。

 so those are big fancy words for a pretty simple idea。

 it turns out that there are other methods that are defined on all objects in Ruby that tell you things about the object。

 like what methods it has and what class it is an instance of。

And if you use those methods at runtime while your program is running。

 you're doing a thing that's often called reflection。

 what you're doing is you're learning things about the program while the program is running。

 like what is the class of this object。😡，That has some uses in programming。

 We will generally avoid those uses。 There's often， but not always a better way to do the same thing。

 What I thought I would show here is that it's sometimes useful in the repple just to explore your program。

 debug it， learn more things about it。 and it's nothing more than method calls on objects。

 So for example， if I say three dot methods。 It turns out I get a very large array of symbols。

 We're gonna to learn arrays soon。 but these are all the methods you can call on three。 Now。

 some of these have to do with arithmetic like three dot suck returns4。 That's the successor method。

3 dot even returns false and so on。 Some of these have nothing to do with numbers。

 They're just methods that were defined in object or some other super class of the class of three。

 So， for example， methods。 that is nothing to do with numbers per se。 Here's something cute。

 you can do。 we could also find out all the methods of nil。



![](img/caec8dcbfb63bec2aef02199ccb04d46_5.png)

![](img/caec8dcbfb63bec2aef02199ccb04d46_6.png)

So it turns out there's quite a few methods on this thing that doesn't even have any useful data。

 And then it turns out that arrays support the subtraction operator。

 So here are all the methods that are part of three and not part of nil。

 And now you will notice if you look at all these that almost all of these have to do with some kind of arithmetic or have something to do with numbers。

 there might still be a couple exceptions in there。

 So the one other thing I showed promise you for reflection is class。

 So it turns out that three is an instance of the fixed them class。

 So when you call the class method， you get that back。 You might be curious， wait a minute。

 is fix numb an object is it have methods。 Yes， it does。 What is its class。😊，Turns out it's class。

 So even classes are objects that have a class。 I could have seen the same thing by just writing three dot class dot class。

 because that's。Just this。Right and then you might ask what's the class of class I mean you almost can't help yourself right and it turns out it's also class so that's a fairly interesting object whose class is the object itself herein lies the road to madness。

 people love to ask questions about what's the class of the class of a class。

 but nonetheless it's an interesting example of this sort of exploratory programming I often find it convenient to look up the methods of an object or a class just here in the repel。

 but then I usually have more questions and I head off to the documentation online to find out more of the details。

And that hopefully gives you a little bit more of a sense of how in Ruby。

 really everything is an object and all code is a method of some class。

