# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p27 26_16_optional-java-mutation -BV1bw4m1D7MM_p27-

In this segment， which is optional， I want to continue our discussion of the benefits of not being able to mutate data by showing you an example in Java So as I said at the end of the previous segment in Ml we can create aliases and not worry about one of those aliases causing an update being used for an update that then affects other aliases。

 but in languages like Java we really have to be careful about where we create aliases versus where we make copies So the example I have here。

 I've simplified so it fits on the slide， but this is the exact idea behind bugs that until they were fixed caused real security violations in real Java libraries。

 including things in the standard Java library related to class loaders and other things So let me walk through what I'm trying to capture the basic idea here So I have some resource which I'll put in the field the resource and I don't want everyone to access this。

 I really want this to be private。

![](img/7d5e2a56bb6b51ad1729ac145c6404a9_1.png)

![](img/7d5e2a56bb6b51ad1729ac145c6404a9_2.png)

So if' used this private field should be hidden， I'm not going to let anyone use it， just anyone。

 but I want some people to be able to access it。 and so I' have something reminiscent of say passwords。

 So the allowed users will just be in this array of strings。 so if someone is in that list。

 then they can use the resource and if not if they try to use the resource。

 I'm going to raise an exception。Now， I'm happy to let everyone know who is allowed to use the resource。

 That's not secret。 Just the contents of the resource are。

 So I have this method get allowed users that will return the string array。

 so you can see who the users are。 You can even see if you're in the list。

 so you're allowed to use it。😊，Could even find out the current user。

 So maybe when the code is executing， there's some notion of a current user。 So that allows the。

 the main method here， if you will， Use the resource to do the right thing。

 So what it's going to do is for every element of the allowed users array。

 It's going to see if the current user。Is the same string as in the IF position of allowed users and so if you find the current user in that array。

 then go ahead， allow access， use the resource in whatever way you're supposed to， otherwise。

 if this for loop actually finishes without returning here in this if statement。

 then throw an exception。Okay， so it turns out this code probably makes sense to you。

 I encourage you to figure out how it's， in fact， insecure。

 And it would let any user who's just a little bit clever to actually use the resource。

 whether they're supposed to or not。 So I'm gonna tell you the answer in a few seconds。

 Click pause if you want。 and don't be too tough on yourself。

 if you can't find the bug since a lot of other people。

 including the people who have written code like this， have made the same mistake。



![](img/7d5e2a56bb6b51ad1729ac145c6404a9_4.png)

Okay， ready， here we go。The Get allowed users method returns an alias to the array。Right。

 so all a malicious user has to do is call getal users to get an alias to the array and then update one of the elements of the array。

 a position 0 to be the current user。 And if you call use the resource。

 I guarantee that name will be in the array。 So clicking back here to the previous slide。

 The error is， in fact， not in use the resource。 That's doing exactly the right thing。

 It's in getal users for leaking an alias to the allowed users's array。 It sort of is like。

 I assume that clients were only going to read this result。

 And in a language that didn't allow you to mutate array elements， that would be a fine assumption。

 But Java is not such a language。 And so clients can do something like this。

 And they'd be able to access the resource。 whether they were supposed to or not。😊。



![](img/7d5e2a56bb6b51ad1729ac145c6404a9_6.png)

![](img/7d5e2a56bb6b51ad1729ac145c6404a9_7.png)

And so the fix， which Java programmers have to remember to do they get no help from the language or the type system unless they use final in the right place or try to use libraries that encapsulate this idea is to change that getal users' method to return a copy of allowed users。

 you have to copy the array so that what's given back to clients can in no way update the internal representation of our private resource object。

 which then causes use the resource to do the wrong thing。 So if that's tough to reason about。

 I agree with you， I find the simplest way to avoid reasoning about that to get rid of mutation for most of the data in my program。

 But if you prefer to have mutation then you get to be in the business of writing your program such that you put copies in all the right places。



![](img/7d5e2a56bb6b51ad1729ac145c6404a9_9.png)