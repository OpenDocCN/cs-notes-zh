# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p157 16_14_subclassing -BV1bw4m1D7MM_p157-

In this segment I want to start talking about subclassing。

 This is essential to object oriented programming and will be a major topic for us in the class。

 so this is really what object oriented programming is all about and since many of you have seen OOP before。

 you've probably seen subclasses in Java， C sharpp。

 C++ Python etc and things in Ruby will be fairly similar but I think it will be useful to study things from a careful programming language perspective and the fact that Ruby is a dynamic language will make things a little bit different and also in many ways a little bit simpler。

So here's the idea of a subclass。 It turns out there's part of a class definition I just didn't tell you about yet。

 which is when you define a class， it always has a superclass。

 so you in the class definition write less than character and then the name of the superclass We've been omitting this in which case the default in Ruby is that it's just like you wrote less than object or object is a class that's provided by default in the Ruy language。

 So what's the purpose of this superclass， it turns out it affects your class definition by including everything in the superclass。

 so any methods defined in the superclass are also methods in the class you're defining with one important exception and that is that the class definition can override some of the methods。

So when you override a method， you just define a different method with the same name and then the subclass has everything in the superclass except the replacements and additions according to the class definition。

 so we say that we inherit the methods from the superclass。

 we get them from our parent class if you will， and then we can make changes to add new methods and replace some of the methods we've inherited。

By the way， if you've seen subclassing in other languages。

 you might be curious about fields or instance variables well that doesn't make any sense in Ruby in Ruby。

 what instance variables， instances of an class have is not part of the class definition as we've seen you're just assigned to instance variables and they come into being and so that happens in any object and nothing is changed once we introduce subclassing when you create an object initially it has no instance variables。

 and then every time you assign to one it comes into being。

I would also point out that in dynamically typed language subclassing has nothing to do with any sort of type system which obviously we don't have Subclassing is purely about what methods are defined in a class。

 which is of course the entire purpose of a class definition。

So let me now show you the example it's already hinted at on the slide here。

 so I have here a class point for representing points on the plane。

 something with an x coordinate and a y coordinate so it turns out that I can use this shorthand notation I've shown you before to define four methods。

 a getter and ater for an X and a getter and a setter for a y。

 so for example this defines a method named X that returns the contents of the at X instance variable。



![](img/d6ffa6a6dce65b55d32629b66faf361e_1.png)

Here is my initialized method， it takes in two arguments。

 maybe it would be easier to understand if I called them A and B。

 and it just creates two instance variables x and y for this object and initializes them to the contents of A and B。

 and then just to keep things short， just two other methods in addition to the four defined on this first line and the initialized method。

 which is the fifth one。How about a method that takes no arguments and reports back the object's distance from the origin from 0。

00 in the plane， and if you remember your basic geometry。

 this is the square root of x squared plus y squared and this first method dis from origin just calls the library method math dot square root with this argument which is using the instance variables to get the x coordinate in the y coordinate multiplying and adding as appropriate。

Very interesting to us in an upcoming segment， So I want to show it here is this second version of disk from origin。

 which I'll just call dis from origin2， that looks very， very similar。

 except here in this expression， I'm actually making four method calls。

 So I'm making calls to self dot X with no arguments and self do Y with no arguments。

 So four method calls in here， instead of the simpler approach and disform origin of just reading the instance variables。

😊，So that's a point。 Now， what about a color point。 So this is a subclass of point。

 And it has everything that a point has。 And then we're going to add two more methods and replace one method。

 So this first line is going to add two methods， a getter and a setter for color。

 So this will define a getter method color and a setter method color equal。

 And then I'm going to replace the initialized method to now be a method that expects either two or three arguments。

And what it does is it first calls， I'll explain this super column in just a minute to initialize the x and Y instance variables。

 and then it sets a color field equal to whatever this C value is。So super is a keyword in Ruby。

 We have similar keywords in many object orary programming languages that says。

 I know I'm replacing my super classes method initialize。

 and I want to my replacement to use the old one as a helper method。 So if I wrote initialize here。

 that would not work。 right， that would be an infinite loop。😊，a method calling itself。

 but super is going to call the initialized method defined in the point class and that will properly initialize the x and y instance variables Okay。

 so that's most of what I wanted to show you Now let's use this here in IRB so I've already loaded the file for you and I could certainly make a point object by just calling the new for point and I can make a color point。

And that will work fine as well， about 0 comma 0 and red。

And I could ask P what it could call the X method on it。 I would get back0。

 and I could call CP dot x， and I would also get0。 I could ask CPp dot color。

 and I would get red if I asked P do color， I will get an undefined method because instances of the point class do not have a method color。

 So that's all fairly straightforward， I thought I would show you a couple other things related to some of the support for reflection in Ruby So you can ask any object。

 what is its class and P is a point， C。Is a color point。But here's something else you can do。

You could say， well， your class is color point， but that object has a method superclass。

 What is the super class of the class color point， It's point。

 We could ask what the super class of that is， It's object。

 We could ask what the super class of that is， its basic object。

 and we could ask the super class of that， it doesn't have one， it's nil。

 if you try to take superclass a n， you'll get an error。

 there is no superclass method defined on the nil object。Okay， so what is what are these things。

 What is a color point， Well， it turns out that if we ask， let's take a regular point。

 there's an is a method that takes a class object and returns true if the object is a point。

 So that returns true。 and now the interesting question is is a color point， C a point。

 and the answer is yes。This is something that subclasssses give us that color point is a color point。

Clearly， but it's also。A point。 And it's also an object。

 So subclass mean the instances of the subclass are also instances of the superclass。 Now。

 there is a different operator in Ruby that makes this distinction。

 If I instead ask if Cp is an instance of point。I get false。

 The only thing CP is an instance of is color point。

 It's exact class not counting any of the super classes。

 So that just shows that there really is a distinction going on here and let me emphasize that just a little bit more with the slide here the code here is mostly what I just showed you maybe with a few slightly different examples。

 and using these methods like is an instance of is actually not particularly OOP style。

 if you use these in your programs， you're giving up things like duck typing you're saying I I'm going to do something different based on whether something is actually a point or actually a color point or maybe just some other object that has methods like getters and setters for X and Y and so on。

 but nonetheless this is an interesting semantic point that we have methods that distinguish from what is your exact class。

 what are you an instance of from including all of your super classes， which is what is。



![](img/d6ffa6a6dce65b55d32629b66faf361e_3.png)

![](img/d6ffa6a6dce65b55d32629b66faf361e_4.png)

Does so an instance of color point is also a point and is also an object。

 And for those of you who come from other languages， this is a little bit confusing， in particular。

 in Java。There's a builtin keyword instance of that is not like the instance underscore of question mark here。

 It's actually like the Ia。 so different languages end up using the same words for exact opposite concepts and such as life。

 Java does not have a built-in keyword for the Ruby's notion of instance of and that's considered a matter of style because Ia is usually what you want to use because that way if you ask is a point。

 you have some object is it a point you'll get true even for any subclasses and that's considered good style because you should be able to use instances of a subclass as though they were instances of the superclass and that's our introduction to subclassing。

