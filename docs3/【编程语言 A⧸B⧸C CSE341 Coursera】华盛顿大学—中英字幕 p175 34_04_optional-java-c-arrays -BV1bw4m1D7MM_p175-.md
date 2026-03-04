# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p175 34_04_optional-java-c-arrays -BV1bw4m1D7MM_p175-

In this optional segment， I want to continue our discussion of depth subtyping by showing how Java and C sharpharp got it wrong for a raise。

 why it did it， what I mean by getting it wrong and how it's okay。

 you can't actually break the soundness of the type system， but it's in a somewhat unusual way。



![](img/c8266b54066fb0cc19623a0969acf8e9_1.png)

So arrays really work like records when it comes to depth subtyping。

 you would be tempted to think that if T1 is a subtype of T2。

 then an array of T1 can be a subtype of an array of T2 and in fact in Java and C sharpharp they allow this subtyping but they should not and here's an example that shows that it should not this code is going to type check but given what I taught you in the previous segment it really shouldn't so let's just assume we have a class point it's going to have an x field in the Y field and a class color point that extends point and adds a color field。

 I've alllighted that here of course。Suppose I have some method that takes in an array of points and we'll get back to what it does。

So now let's use that method as follows， let's make an array of color points of some length。

 so CPptT array will be an array of color points， how about I initialize it with this four loop here。

 so my C point array， every element from zero up to the size of the array holds a color point。

 which is what it should hold because I have a color point array。Now。

 when I call M1 with that color point array， look at what M1 does。

 it assigns into that array a point。This is exactly the same problem as we saw before。

 we're taking an array of things that should have the subtype color point。

 and we're updating one of those things hold a point instead。 So after that call。

 if I try to read the color field of the color point thing in there It doesn't have a color field。

 that index0 of the array was updated to hold a point。

 not a color point and it simply does not have this field。 So something here has gone very。

 very wrong。 either Javas type system is broken or I'm lying to you and this actually doesn't type check or they do something different。

 turns out they do something different。 this does type check but it really shouldn't。

 And what they do instead， it turns out if you run this code， you will get an exception。

 and it's probably not where you think you would get an exception。

 I'll show you that in just a second。

![](img/c8266b54066fb0cc19623a0969acf8e9_3.png)

So why did they do this Well， it turns out that if you have a more flexible type system。

 it allows more programs and we know that having this subdping rule would allow lots of good programs。

 it just happens to also allow some bad programs like I saw in the previous slide and those good programs were considered really important。

 especially before Java had generic types， things like M's polymorphism if they didn't have this rule it would have not been possible to write a general sorting routine that worked for any kind of object and that was just considered too restrictive now that frankly Java and C sharpharp have generics。

 I think that this design decision is far more questionable， but it is a matter of reasonable debate。

 I suppose。Now， the good news is， despite this inappropriate depth subtyping。

 this depth subtyping that is not right based on what we learned。

 it turns out you're never going to have the read or write of a field fail。

And you're never going to have an array read fail because of having the wrong type Now we know that E dot color can fail if E is null。

 we know that E1 E2 can fail if the index E2 is out of bounds。

 but neither of those are really subtyping issues。😡，Instead。

 what they decided to do in Java and C sharpp is potentially have array updates fail in Java。

 if you didn't know this， you're about to learn。E1 bracket E2 equals E3。

 updating an array that can fail。Even if E1 has type array of T， even if E3 has type T。

 and even if E2 is within bounds， is a perfectly reasonable number like0。Instead。

 what happens in Java is when you store into an array。At runtime， it kind of retype checks things。

 if you will。 And it checks that the runtime class of E1's elements。

 the kind of array that E1 actually evaluated to。Is something that can have elements in it of the object that E3 has。

 So it takes the runtime class of E3， the runtime class of E1's elements and does a check to make sure that E3's class is as a subclass is a subtype of E1's type。

So you're not getting any static help here if you mess this up like we did on the previous slide。

 you're going to get a runtime exception， it's actually called an array store exception。

 and it has to be in there because otherwise depth subtittan would be unsound and our program would be even less predictable than with this。

😡。

![](img/c8266b54066fb0cc19623a0969acf8e9_5.png)

So here's what actually happens in our example， here's most of the code I've alllighted the initialization of the colorPo array。

So we create V array that works fine。 we initialize it here in this dot dot dot， that works fine。Now。

 right here， when we call M1 with the color point array， we go up here。

 even though point array has type point bracket bracket。

 it's actually in the environment bound to an array of color points。So right here in this assignment。

 when we assign a point into what is actually a colorPo array。

 we get an exception so we get an exception on this line in the body of M1。

 even though you can look at M1 all day long and not see any problem with doing this。

 this is where you get the exception， you get the exception here。

 but it's because the caller did some subtyping that was inappropriate or highly questionable。

So as a result， we never get to the rest of the code， if we do return from M1。

 then we know that M1 has some different implementation that doesn't do this sort of illegal update and therefore colorpointin array still holds an array of color points。

 and so we can read out of it， access the color field， and so on。😡，So that's what's going on in Java。

 that is why they allow this array subtyping， they traded it。

 they allow the array subtyping at the expense of doing these checks on all array stores。

 every update to an array does this check and may raise an exception。

As long as we're picking on Java and C sharprp， how about one slide about null？

So array doors are probably the most surprising thing。

 a lot of people don't even realize that these languages work this way。

 but everyone seems to be comfortable with null。 So null is just this constant。

 It's a keyword in these languages that is not an object that doesn't have any fields or methods。

 So from a subtyping perspective， it should be a super。

 it should have a type that is a super type of everything， right， something that has no methods。

 no fields is like an empty record， and a record with fewer things。

 according to with subtyping should be the super type。

Instead it works the other way in Java and C sharphar， null can have any object type。

 it's like there's a type for null that is a subtype of everything。And that does not make sense。

 in the sense of it's not like null has type string and null has type 3D color point， except it does。

 And as a result， whenever you read a field or call a method in Java C sharp。

 you might get a null pointer exception again， because the static type system is not preventing things that could cause a problem。

 we have to check them dynamically instead。 And that's why according to the language semantics。

 every method call and every field access has to check whether the receiver is actually null。

 And if so， throw a null pointer exception。Now this is done for good reason in the language。

 it's awkward not to have it， and it provides more convenience and null is convenient in all the ways that we're used to using it。

But it means that our static type checker never prevents this error， and it would certainly be nice。

 and a lot of people have tried this in various language designs to separate out the idea of types that could be null from types that definitely are not null and being able to check statically that certain expressions in your program will not evaluate to null means that those expressions don't suffer from null pointer exceptions。

 and it's one less thing you have to test for or worry about happening at runtime。

I would also note that M chose to take a different decision ML does not have something like null when you want the possibility of not having data。

 you use ML's option types and while they're a little less convenient to use than Javas null you know what you're doing and you know that all the other things in your program are not possibly null so it's an interesting design choice to have null。

 I would certainly be in favor of adding cannot possibly be null types to modern languages and maybe we'll get there someday。

😡。

![](img/c8266b54066fb0cc19623a0969acf8e9_7.png)