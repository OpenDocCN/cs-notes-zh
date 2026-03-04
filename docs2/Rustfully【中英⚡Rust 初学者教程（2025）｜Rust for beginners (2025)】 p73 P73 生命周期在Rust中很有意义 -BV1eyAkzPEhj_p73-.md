# Rustfully【中英⚡Rust 初学者教程（2025）｜Rust for beginners (2025)】 p73 P73 生命周期在Rust中很有意义 -BV1eyAkzPEhj_p73-

In this video， we're going to continue learning about lifetime all rules。

 The compiler uses three rules to figure out the lifetimes of the references when they aren't explicit annotations。

 The first rule applies to input lifetimes。 and the second and third rules apply to output lifetimes。

 If the compiler gets to the end of the three rules and there are still references for which you can't figure out lifetimes。

 the compiler will stop with an error。 The first rule is that the compiler assigns a lifetime parameter to each parameter。

 that's a reference。 In other words， a function with one parameter gets one lifetime parameter。

 a function with two parameter gets two separate lifetime parameter。 and so on。

 The second rule is that if there is exactly one input lifetime parameter。

 that lifetime is assigned to all output lifetime parameters。 As you can see here in this example。

 we have only one input lifetime parameter， which means that lifetime is going to be assigned to the output parameter。

 The third rule is that if there are。😊。

![](img/aa1b8f0b9fa0250d854307e15ac5a015_1.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_2.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_3.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_4.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_5.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_6.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_7.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_8.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_9.png)

Multiple input lifetime parameters， but one of them is a reference to self or a mut reference to self because this is a method。

 the lifetime of self is assigned to all output lifetime parameters this third rule makes methods much nicer to read and write because fewer symbols are necessary let's pretend where the compiler will apply these rules to figure out the lifetimes of the references in the signature of the first word function。

 The signature starts without any lifetimes associated with the references then the compiler applies the first rule which specifies that each parameter gets its own lifetime we'll call it a as usual right now you see the inferred lifetime annotations because that's what rust sees when it infers this we're going to manually type them in So here we can add the lifetime annotation of a and we'll pass it here as well The second rule applies because there is exactly one input lifetime The second rule specifies that the lifetime of the one。



![](img/aa1b8f0b9fa0250d854307e15ac5a015_11.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_12.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_13.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_14.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_15.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_16.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_17.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_18.png)

Input parameter gets assigned to the output lifetime。

 So that's why the lifetime parameter A is assigned to the output。 Once again。

 my code editor can infer this or rust can infer this and show it to my code editor。

 So I get it in gray but we can explicitly add that Now all the references in this function signature have lifetimes and the compiler can continue its analysis without needing the programmer to annotate the lifetimes in this function signature。

 anyway， we don't need to explicitly specify them here because rust can easily infer them。

 but now let's look at another example。 And this time we're going to use the longest function。

 Let's start off by applying the first rule Each parameter gets its own lifetime。

 This time we have two parameters instead of one so we have two lifetimes which means it's going to look like this here we're going to have A and B。

 the first one gets A and the second one gets B you can see that the second rule doesn't apply because there is more than one input lifetime The third rule doesn't apply。



![](img/aa1b8f0b9fa0250d854307e15ac5a015_20.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_21.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_22.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_23.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_24.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_25.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_26.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_27.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_28.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_29.png)

Either because longest is a function rather than a method。 So none of the parameters are self。

 After working through all three rules， we still haven't figured out what the return types lifetime is。

 This is why we get an error trying to compile the code without lifetime annotations。

 Or in this example， it would be much better to actually return something so you could see it for yourself。



![](img/aa1b8f0b9fa0250d854307e15ac5a015_31.png)

Now we're getting a proper error because we are missing a lifetime specifier。

 The compiler worked through the lifetime all rules。

 but still couldn't figure out all the lifetimes of the references in the signature so we need to add explicit lifetime annotations and pretty much all we need to do here is specify that we want to return a string attached to lifetime A and then we can remove this part here and say that this is also attached to lifetime A and that would fix everything but now let's move on to lifetimes in method definitions when we implement methods on astruct with lifetimes we use the same syntax as that of generic type parameters where we declare and use the lifetime parameters depends on whether they're related to thestruct fields or the method parameters and return values lifetime names forstruct fields always need to be declared after the imp keyword and then used after thestruct name because those lifetimes are part of thestruct type So let's go back to our。



![](img/aa1b8f0b9fa0250d854307e15ac5a015_33.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_34.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_35.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_36.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_37.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_38.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_39.png)

Important to excerpt example， as you can see here we define the lifetime annotation and we attach it to the part in method signatures inside the I block。

 references might be tied to the lifetime of references in thestructs field or they might be independent In addition。

 the lifetime e rules often make it so that lifetime annotations aren't necessary in method signatures First we'll use a method named level whose only parameter is a reference to self and whose return value is an I32 which is not a reference to anything the lifetime parameter declaration after I and its use after the type name are required。

 but because of the first illusion rule were not required to annotate the lifetime of the reference to self Here's an example where the third lifetime e rule applies and I've zoomed out quite a bit because my code editor gave me quite long lifetime names but here we have two。



![](img/aa1b8f0b9fa0250d854307e15ac5a015_41.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_42.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_43.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_44.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_45.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_46.png)

Lis So Ru applies the first lifetime all rule and gives both self and announcement their own lifetimes。

 Then because one of the parameters is a reference to self。

 the return type gets the lifetime of self as you can see over here and all lifetimes have been accounted for。

 This is why methods are often easier to work with than standalone functions when it comes to lifetimes。

 The third illusion rule handles a lot of common cases automatically personally I find the lifetime all rules really helpful because they let me write less boilerplate code。

 Most of the time the compiler can figure out what I mean and when it can't it gives me a clear error message telling me exactly what lifetime annotations I need to add。



![](img/aa1b8f0b9fa0250d854307e15ac5a015_48.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_49.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_50.png)

![](img/aa1b8f0b9fa0250d854307e15ac5a015_51.png)