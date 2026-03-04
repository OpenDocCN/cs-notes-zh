# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P67：-067-Includes Chap5 Video 15.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's see how another feature of Ocamel's module system includes。

Allows us to avoid having to duplicate code。We've seen in the past how OcaMel uses different operators for integer arithmetic versus floating point arithmetic。

Suppose we wanted to entry to some module that abstracts those so that they both look kind of the same。

If you've ever taken abstract algebra， you know that there are structures called rings and fields that do just this。

Now I'm not going to go into any details of abstract algebra here so don't worry if you haven't taken such a class the only thing you need to know is that a ring basically is of mathematical structure with addition and multiplication and a field also adds di。

So here we have a signature for rings。It has a type T。

 which is whatever the underlying mathematical type is， and then it has abstract values for 0 and1。

And operators for addition multiplication and uninary negation。

 putting the Tilde in front of it makes it unary。And finally。

 we have a function to convert whatever the value is to a string so that we can display it。

I could represent integer rings with this module， T is now an int， 0 and1 or the usual 0 and1。

 and all of the operators of the usual standard library operators for integers to convert to a string。

 I could just use string in。Finally， I could create an int ring here。

 which is sealed at that ring signature and make it int ring rep。

So let's pause there and see how this works。The zero value from entering is abstract because it's been sealed。

Of course， in the unsealed version of it， we can see that it's zero。

If you want to be able to tell what that zero actually is from the sealed version of it， you could。

Use the string function that's part of the module to convert it to a string and see it that way。

 We could add together images this way。That gets us zero。So does that？

So we've abstracted away a bit from integers。We could do the same thing with floating point numbers here I have a float ring representation that uses floats and zero dot and one dot and all the dot versions of these standard library operators。

That flow ring。Would work just the same as the an ring we've already seen。



![](img/549d53aa3f8aad8b5b7b7bf5ef9f606c_1.png)

Now we're getting zero dot as the answer， but notice we didn't have to change in the operators right we don't have to write plus dot now。

 we've hidden that behind the interface and provided the operators through that interface Now we don't have division yet。

Technically speaking division is part of a field， not part of a ring。

So suppose we wanted to implement fields and also provide division。One way to do that。

 not a good way， would be to copy code。😡，Now I have an int field and I could do division in it。

But I've duplicated a lot of code from that ring module code duplication leads to unmatainable code。

If someone wants to make a change in the ring implementation。

 now they also have to duplicate that change in the field implementation that's no good。

 that's why OMm has a feature calledIns。We can just include all the contents of another signature our structure in a new one that we're defining。

With the includes that I just added。The effect is the same as the code we had written before。

 it's just we get rid of the code duplication。😡，Include R is saying include all of the declarations that are already in R as part of module type field。

Include int ring rep is saying includelude all the definitions that were part of int ring rep as part of the module int field rep。

 and now if anyone were ever to come along and add new operation to rings or change the implementations of the ring operations in in ring rep。

 we would automatically get all of those changes reflected in our int field rep here as well。

We can do the same thing with float fields。One thing to watch out for here is that we really did need to include int ring rep。

 which was the unsealed version rather than int ring in this implementation。

 if we only include int ring。Then the output of this module， the values in it。

 notice that almost everything in it has type T except for the division operation。

 which now has types involving int。So it's not known inside of the implementation of int field rep that T and int ought to be the same thing and in fact really are because int ring was sealed at the module type ring。

 it's been hidden at this point that its internal implementation is with an int and that's why we're getting a compilation error here。

 there's a signature mismatch， the division operation that's provided by int field rep has the int type as part of it。

 but what's expected for the field is to have T as part of it。We can fix that。

By making sure to include the unsealed version here。



![](img/549d53aa3f8aad8b5b7b7bf5ef9f606c_3.png)