# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p177 36_06_subtyping-for-oop -BV1bw4m1D7MM_p177-

In this segment， I want to continue talking about subtyping。

 but now talk about object oriented programming。 This is a good way to do it。

 We've learned the theory of how subtyping should work for records and for functions。

 we can actually use that to understand how classbased object oriented programming can have a static type checker and this is really how the core techniques used to type check languages like Java and C sharpp。



![](img/3b482008e007c103b897ab8a76150fd6_1.png)

So as I mentioned back when we studied interfaces in these languages， the class names are also types。

 so Ruby doesn't have types， but in these languages when you declare a class C。

 you also get a type C and the subclass relationship is also the subtype relationship if C is a subclass of D than the type C is a subtype of D and because we have transitive subtyping in fact。

 you're a subtype of anything higher than you in the subclass hierarchy all the way up to object at the top。

So if we're going to do this， we need to obey our substitution principle and we have to make sure that any instance of a subclass could be used anywhere an instance of a superclass appears without anyone ever calling a method that doesn't exist or accessing a field that doesn't exist where fields are like instance variables but in these languages they actually are part of the class definition。

 so they're part of the type that comes along with those classes。So the way to think about this。

 the way we've studied subtyping is that objects are essentially records， they're a little different。

 I'll explain that at the end， but they have a bunch of fields in them。

 they have a bunch of methods in them， and you can think of the variables for the field name and the name of the method is just the names of the record slots。

 the record fields。

![](img/3b482008e007c103b897ab8a76150fd6_3.png)

And the thing that drives our subtyping is that the fields are generally mutable。

So we know that depth subtyping is not going to be sound on those。

 but the methods are typically immutable， so we can have subtyping on the methods。

 and the methods are like functions。 So our rules for contravariance and covariance flipping around the argument。

 same way for the result is how we can reason about how a subclass can change the type of a method So you really could design a type system for an object ored programming language using this idea of record types in your subtypes you would allow extra fields and methods just like subclasss always do。

 you're allowed to add new fields and methods and we know from our study of width subtyping that that will be sound that we can use an instance of the subclass as though it's an instance of the superclass because you know no code will care if the object has some extra things that the type doesn't promise that it has。

And we know that if you're overriding a method。😡，That the new method， which is like a function。

 better be able to be used wherever the superclass's method could be used。

 and that means the arguments will have to be contravariant in the subtype。

 the arguments will have to be super types of what they were in the superclass。

 but the return type is covariant， there' the jargon means that the subclass。

 the overriding method can use a subtype of the type that the superclass method used for the return type。

 and this is all sound related to depth subtiming because you can't update a method to be some other method in these languages。



![](img/3b482008e007c103b897ab8a76150fd6_5.png)

So that would all work。 it turns out if you actually look at a Java and C sharpp。

 it kind of does this and then it makes some slightly different decisions and that's fine。

 so it doesn't use types like R record types， you never see something like X colon real Y colon real。

 they just reuse the class names or with interfaces like I showed you the interface names so they have names for types rather than writing out the contents of the classes。

 that's okay。That actually does restrict subtyping。

 so suppose I had a color point class and I had a point class。

 but I did not say that color point was a subclass of point。

 I just reimplemented everything that point had。Well from a type soundness perspective。

 it would be fine for color point to be a subtype of point， but in Java and C sharpp。

 it does not get to be if you want to be one type to be a subtype of another type and those types are both names of classes。

 you have to actually be related in the subclassing relationship。

 you can't just happen to have all the things that the other class has and so that's a subset of what would be okay and whenever you're more restrictive than what would be okay。

 that's okay。So we know that a subclass number two here can add fields and methods that works fine。

 that's exactly how these languages work。And we know that a subclass can override a method and make the return type。

 a subtype， and these languages allow that。Now we could allow an overriding method to change the argument types as long as we are contravarit。

 we were flipped around， but these languages choose not to do that。

 they make a different design choice they say that if you change the argument types here're not actually overriding at all Instead you're just creating a different method with the same name and we know that you can add methods so that doesn't cause a problem and this issue of having multiple methods with the same name is this static overloading I've mentioned once or twice in the lectures and I'm not going into the details of exactly how it works because it's just complicated without adding that much interesting concepts to the study of programming languages。



![](img/3b482008e007c103b897ab8a76150fd6_7.png)

If I could get you to improve your terminology in one way related to object oriented programming。

 it would probably be to teach you the distinction between classes and types。

 and this is a little difficult because Java and C sharpp purposely confuse them by making every class also be a type。

 but let me give it a try anyway。A class is what defines an object's behavior。

 These are the things we defined in Ruby， right， Every object has a class， a class defines behavior。

 a class has method definitions with bodies that have code that return things。

A type describes in objects， methods， arguments， and result types。It says。

Some object that has this type has a method fo that takes a string and returns an object or something like that right it has a type describes what the object has in terms of methods and their types and a subtype is something that is substitutable in terms of those methods and their types and these are actually separate concepts you could have two types that are not related to classes or two classes that are not related to types。

 but for good reasons of convenience， most statically typed classbased object oriented languages。

 choose to confuse these ideas by reusing class names as type names and then the type represented by some class name is the type that well go find all the methods in the class definition。

 read out their argument types and their result types and that's the type we need and this is very convenient in practice but as a matter of terminology。

 classes are about behavior。And types are about interfaces。

 about what you can take and what you return。

![](img/3b482008e007c103b897ab8a76150fd6_9.png)

Couple optional things that are relevant to this segment， but they're more details。

 and they're not things that you need to learn。 This is not very interesting。

 but Java and C sharpharp are perfectly sound。 right The way there's subtyping and subclassing work。

 as long as you don't have explicit downcasts， which I'm not getting into here。

 all work whenever you call a method M on some expression， If that expression is not null。

 then the receiving object actually has a method M。 It gets it right。

 but various times when you're program these languages。

 you run into details where you really think it got it wrong。

 Here's one that I stumbled across a couple years ago。

 it's just because I did not know Java as well as I thought I did。

Let's say that a super class declares some field， it has type some type。

So you would think that if the subclass is going to have that field。

 it would have to have the same type because fields are mutable， we know from depth subtyping。

 you can't change it。Well， it turns out in Java， the superclass and the subclass both define a field with the same name。

 say fo。Then you can do that and the two declarations of the field can have totally different and unrelated types。

 and it all goes through the type checker and everything seems to work fine。

And I was really confused about this and turns out what happens， Java decided that if you do that。

 you just have two fields named F in the same object。

And the only question now is well when you say foo。

 which field are you talking about and what they decide is that in the superclass。

 you're talking about the one defined in the superclass and the subclass。

 you're talking about the one defined find in the subclass and there may be various ways to get at the other one if you really need to I'm not sure that there is actually but that resolved my confusion so I thought they were doing something on sound。

 but when you're confused， you don't just keep trying things out you go and get the language manual and you read about what they're actually doing and you know the people who design Java are fairly smart they would not do something。

 they would break the soundness of their type system。

 even if occasionally you use some feature you didn't realize you were using and you find it a little confusing。



![](img/3b482008e007c103b897ab8a76150fd6_11.png)

That was optional topic number one， this one， if you're still with me， you may find more interesting。

 which is that self， Ruby's self， or what Java and C sharprp and C++ called this is actually special。

That if you think of it as an argument and you very well mind because back when we encoded OOP and rackcet。

 remember how our functions took an extra argument that was self。

 if you think of self as an argument to methods， then it's a very special argument。

 because it gets to be treated covariantly， even though all the other arguments like I spent the previous segment on have to be contravariant。

So there's an example here， suppose you have some class A with a method M，If class B。

 which is a subclass of a， overrides M。😡，In M， in the subclass， we get to know that self is a B。

 We get to know down here in the bottom M that there's a field X and we can use it。

 We can even return it。 Okay that only works if self is covariant that somehow self。

 if you think of it as an argument， in the subclass gets to be a B， even though in the superclass。

 we only know it's an A。 and that's actually covariance， it's not contravariance， So is this unsound。

 And it turns out it is not unsound， because it's not a normal argument。

It's not something where callers of M can choose what object to pass。 they have to pass self。

 It has to be the entire object。 So whenever this bottom M is evaluated。

 we know that self will be an instance of B， and so it's fine to assume that even though in the superclass。

 we did not know that we only know that in the subclass。😡。

And so that is our study of taking everything we learned about subdiping in a more careful and precise environment and seeing how it actually explains a lot of how type systems work in object oriented languages。



![](img/3b482008e007c103b897ab8a76150fd6_13.png)