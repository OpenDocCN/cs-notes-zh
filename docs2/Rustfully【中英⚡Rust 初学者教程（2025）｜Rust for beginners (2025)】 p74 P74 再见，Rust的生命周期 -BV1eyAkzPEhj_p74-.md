# Rustfully【中英⚡Rust 初学者教程（2025）｜Rust for beginners (2025)】 p74 P74 再见，Rust的生命周期 -BV1eyAkzPEhj_p74-

One special lifetime we need to discuss is static， which denotes that the affected reference can live for the entire duration of the program。

 all string literals have the static lifetime， which we can annotate as follows the text of a string literal is stored directly in the program binary。

 which is always available therefore the lifetime of all string literals is static even this one over here is going to be a static string literal Now you might see suggestions in error messages to use the static lifetime but before specifying static as the lifetime for a reference think about whether or not the reference you have actually lives the entire lifetime of your program and whether you want it to most of the time an error message suggesting the static lifetime results from attempting to create a dangling reference or a mismatch of the available lifetimes in such cases the solution is to fix those problems。



![](img/2b125f82f65597918ffb9a2151a8b0c2_1.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_2.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_3.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_4.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_5.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_6.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_7.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_8.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_9.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_10.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_11.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_12.png)

Not to specify the static lifetime。 personally， I recommend being very careful with static。

 It's easy to think you need it when you actually just need to fix your lifetime annotations。

 Let's briefly look at syntax of specifying generic type parameters。

 trait bounds and lifetimes all in one function。 This is the longest function we've seen before。

 but now it has an extra parameter of a generic type to create this function。

 We're going to use the display trait。 Then we're going to create a function called longest with an announcement。

 And here we're specifying the lifetime。 and the generic type。 Then this is going to return a string。

 and we're not done yet because below it， we're going to return a string where T follows the display trait。

 So this is the longest function that returns the longer of two string slices。

 But now it has an extra parameter named an of the generic type T。

 which can be filled in by any type that implements。😊。



![](img/2b125f82f65597918ffb9a2151a8b0c2_14.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_15.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_16.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_17.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_18.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_19.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_20.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_21.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_22.png)

The display trait as specified by the wear clause， this extra parameter will be printed using curly braces。

 which is why the display trade bound is necessary because lifetimes are a type of generic the declarations of the lifetime parameter A and the generic type parameter T go in the same list inside the angle brackets after the function name。

 The order of generic parameters is lifetimes first than types then constant generics if any。

 this is a convention that makes code more readable and consistent across the rust ecosystem Now that you know about generic type parameters。

 traits and trade bounds and generic lifetime parameters。

 you're ready to write code without repetition that works in many different situations generic type parameters let you apply the code to different types trait and trade bounds ensure that even though the types are generic。

 they'll have the behavior the code needs。

![](img/2b125f82f65597918ffb9a2151a8b0c2_24.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_25.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_26.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_27.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_28.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_29.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_30.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_31.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_32.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_33.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_34.png)

How to use lifetime annotations to ensure that this flexible code won't have any dangling references and all of this analysis happens at compile time。

 which doesn't affect runtime performance。 So once again this function demonstrates lifetime parameters。

 generic type parameters trade bounds all working together in one function signature although my recommendation is to start simple and add complexity as needed。

 don't try to use all of these features at once unless you really need to Most of the time you can get away with simpler code and the compiler will help you when you need to add more annotations Now there's a lot more we can learn regarding lifetimes there are also more complex scenarios involving lifetime annotations that you will only need in very advanced scenarios but for most rust code what we've covered here will be sufficient So at this point we're going to say goodbye to rust lifetimes and we will revisit the。



![](img/2b125f82f65597918ffb9a2151a8b0c2_36.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_37.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_38.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_39.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_40.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_41.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_42.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_43.png)

![](img/2b125f82f65597918ffb9a2151a8b0c2_44.png)

Oject in a future video。