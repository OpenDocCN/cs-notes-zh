# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P61：-061-Module Types and Signatures Chap5 Video 9.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

![](img/05da4a05b7ef9412a225cdff0290ee80_0.png)

An interface is a collection of names and specifications about those names。

 typically they're related in some way such that the entirety of the interface makes sense as a unit of code。



![](img/05da4a05b7ef9412a225cdff0290ee80_2.png)

![](img/05da4a05b7ef9412a225cdff0290ee80_3.png)

You've been used to interfaces in Java， Ocael has a similar feature called signatures。



![](img/05da4a05b7ef9412a225cdff0290ee80_5.png)

Let's write a signature for modules that have a factorial function。



![](img/05da4a05b7ef9412a225cdff0290ee80_7.png)

You'll see right away that this looks a lot like a definition of a module with a few changes。



![](img/05da4a05b7ef9412a225cdff0290ee80_9.png)

First we say module type because we're here specifying what the type of a module has to be。

 not the value of a module。

![](img/05da4a05b7ef9412a225cdff0290ee80_11.png)

![](img/05da4a05b7ef9412a225cdff0290ee80_12.png)

The block that defines that module type is a signature。



![](img/05da4a05b7ef9412a225cdff0290ee80_14.png)

Beginning with the key word Sig and ending with end。



![](img/05da4a05b7ef9412a225cdff0290ee80_16.png)

Inside the signature you provide specifications of the names and types and behaviors of all the values that will be in any module of this type。



![](img/05da4a05b7ef9412a225cdff0290ee80_18.png)

![](img/05da4a05b7ef9412a225cdff0290ee80_19.png)

Here I've said there must be a value fact， which has type int arrow int。



![](img/05da4a05b7ef9412a225cdff0290ee80_21.png)

And I've provided a specification comment for it， factact N is n factorial。



![](img/05da4a05b7ef9412a225cdff0290ee80_23.png)

Now notice the use of the vowel keyword here， you've seen that before in U anytime we create a value。



![](img/05da4a05b7ef9412a225cdff0290ee80_25.png)

![](img/05da4a05b7ef9412a225cdff0290ee80_26.png)

UT responds by saying there's a value named X with type in and what its value is It's the same sense in which the value keyword is being used here to say that there is a value named fact and its type is enter Oent it's just not we're not saying what the value actually is in our module type。



![](img/05da4a05b7ef9412a225cdff0290ee80_28.png)

I could provide modules that have this type。

![](img/05da4a05b7ef9412a225cdff0290ee80_30.png)

![](img/05da4a05b7ef9412a225cdff0290ee80_31.png)

This module named recursive fact， has module type fact。

And it implements that module by providing the definition of a name fact with the correct type。

Of course， the type checker is going to check that the type is correct。

 I couldn't return a string here。For example。There's no way for OCMel's compiler to check that this really is the factorial function。

 the correctness of the code with respect to that。Documentation comment is not being checked。

 of course。Note that the comment does go in the module type， not the module。

The module type is where we document all of the specifications about what functions are supposed to do for the rest of the world。

This is where the clients go to read documentation of the type。

So documentation is factored in OcaMl between the interface and the implementation。

 the documentation in the interface is the kind of public facing documentation for the world to see about how the function is supposed to behave the module type requires there to be a function named fact。

 other functions won't do。

![](img/05da4a05b7ef9412a225cdff0290ee80_33.png)

I get a type checking error here。😡，A signature mismatch， the modules do not match。

Val ink of type intarrow int is not included。😡，In fact。The value fact is required but not provided。

So that rather lengthy error message is saying there's a value named fact that is required by this module type annotation here。

 but it is not being provided by a structure that is purportedly implementing that interface。

I could have other modules that implement the same interface。

This tail recursive module implementing the factorial interface does provide a factorial function。

And I can use that factorial function from outside of the module。

But one thing I can't do is use the helper function。Unbound value， tail recursive fact。 fact。

When we put the module type annotation on this module。

We're not only saying that it must provide all of the names from that interface。

 We're saying those are the only ones that will be exposed to the rest of the world。

So because fact only mentions the function fact， not the function fact ox。

 fact ox is kept hidden inside of tail recursive fact。Now if I removed the module type annotation。

Then that compilation error would go away because fact do is no longer being hidden behind that inner。

