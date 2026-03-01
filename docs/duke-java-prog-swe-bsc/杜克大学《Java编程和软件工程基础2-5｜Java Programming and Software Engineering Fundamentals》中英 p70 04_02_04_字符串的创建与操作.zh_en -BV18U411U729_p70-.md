# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p70 04_02_04_字符串的创建与操作.zh_en -BV18U411U729_p70-

![](img/392e4a89ec9090f32cc44b0826816ba1_0.png)

Welcome back now that you know a little bit about how a Caar cipher works。

 it is time to expand your Java knowledge so that you can implement one。



![](img/392e4a89ec9090f32cc44b0826816ba1_2.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_3.png)

You should know something about strings already if you took our previous course Java programming。

 solving problems with software， you learned how to manipulate strings。

 If you are unfamiliar with strings， we recommend you brush up on them before proceeding。



![](img/392e4a89ec9090f32cc44b0826816ba1_5.png)

However， to perform encryption， you need to do something with strings that you did not do in the previous course。

 In that course， you analyzed the contents of strings and operated on pieces of existing strings。

 However， you did not build up new strings。

![](img/392e4a89ec9090f32cc44b0826816ba1_7.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_8.png)

If you carefully reexamine what you saw about how a seizure cipher works。

 you will see that you are making a new string by adding one character at a time。



![](img/392e4a89ec9090f32cc44b0826816ba1_10.png)

One way that you can build up a string is with concatetnation。

 which is a fancy word for sticking things together In Java。

 you can perform string concatetnation with a plus operator whenever at least one operaand is a string。

 If one operaand is a string， but the other is not。

 then the concatenation operator figures out the string representation of the non string operaand and concateates that。



![](img/392e4a89ec9090f32cc44b0826816ba1_12.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_13.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_14.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_15.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_16.png)

For example， if you were to write these two strings with the plus operator between them。

 you would be telling Java to perform string concatenation。



![](img/392e4a89ec9090f32cc44b0826816ba1_18.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_19.png)

The result would be the string you see here， which was formed by sticking these strings together。

 exactly what concatenation means。To illustrate the usefulness of this operation。

 think about the Caar cipher you are working on。 You might want to take the original alphabet as a string and make a rearranged alphabet based on the key。

 You could do that by taking two pieces with substr。

 which you are already familiar with and concatenating them together。



![](img/392e4a89ec9090f32cc44b0826816ba1_21.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_22.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_23.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_24.png)

First， you would take the substr starting at 23。 Remember that substr with only one argument。

 returns the substr starting at the specified position and going all the way to the end of the string。

Then you would concatenate the substring from 0 to 23 onto the end of that string。

Now you have two strings which describe the mapping from each plain text letter to the appropriate ciphertext letter。

We did this for the key of 23， but you should think for a moment about how you would generalize this for other keys。

As you learn more about manipulating strings， it is important to know that they are immutable。

 you cannot change an existing string once it has been created。



![](img/392e4a89ec9090f32cc44b0826816ba1_26.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_27.png)

Instead， if you want a different string， you must make a new one with that change。

 This concept may seem a bit confusing and subtle， so it helps to see it with a picture。



![](img/392e4a89ec9090f32cc44b0826816ba1_29.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_30.png)

Here we have declared a string and initialized it to Ho。 Nothing new or surprising here。



![](img/392e4a89ec9090f32cc44b0826816ba1_32.png)

A common practice is to draw a picture of the effect of this statement by drawing a box for the variable S。



![](img/392e4a89ec9090f32cc44b0826816ba1_34.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_35.png)

And making an arrow pointing to the letters that make up the string hello。

If you declare another string X and initialize it with S。

 you would have a picture that looks like this。

![](img/392e4a89ec9090f32cc44b0826816ba1_37.png)

Both X and S refer to the same string。

![](img/392e4a89ec9090f32cc44b0826816ba1_39.png)

Now， suppose you did S equals S plus space world。 That is you compute S concatenated with the string space world。

 You are not changing the existing string， but rather making another string。

 which involves copying the existing strings like this。



![](img/392e4a89ec9090f32cc44b0826816ba1_41.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_42.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_43.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_44.png)

Notice that x is still hello because you did not change the existing string。

 you made a different string and assigned it to S。If you do a lot of string concateation operations on large strings。

 especially， the required copying can be quite slow and inefficient。

 even though we are not terribly focused on the most efficient way to do things yet。

 it is still a good practice to develop good habits。If you are building。

Large strings by adding many small pieces， you want to use a different approach。In fact。

 Java has a string builder class specifically for this purpose。

 it provides a mutable sequence of characters， meaning it is like a string， but you can modify it。

 changing and inserting characters in an efficient way。



![](img/392e4a89ec9090f32cc44b0826816ba1_46.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_47.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_48.png)

When you create a new string builder， you can pass a string in to specify its initial contents。

 There are also many useful methods。 We will name just a few of the most important ones。

 but recommend you consult the API documentation for a full list and more details。



![](img/392e4a89ec9090f32cc44b0826816ba1_50.png)

One useful method is a pen， which lets you put a string on the end。

 You could also pass in other types of data， which will be converted to a string before being added to the end。

You can insert a string or the string representation of other types of data at any location you want。

 you can get or set individual characters by their index。

 the numerical location where they are in the sequence of characters。

When you are done manipulating the string buffer， you will often want to use two string to get the string you have made。

As before， it helps to see a picture of how these methods operate here。

 We have started by creating a string builder and passing in the string。 Hello。

 We have drawn this picture with S B， having an arrow pointing to the sequence of characters in the string builder。



![](img/392e4a89ec9090f32cc44b0826816ba1_52.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_53.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_54.png)

Now， if you call SB do append and pass in world， you will modify the existing sequence of characters。

 notice how we change the existing sequence rather than copying them into a new sequence。



![](img/392e4a89ec9090f32cc44b0826816ba1_56.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_57.png)

You could also insert or put the characters into the middle。

 which would still modify the same sequence of characters like this。



![](img/392e4a89ec9090f32cc44b0826816ba1_59.png)

![](img/392e4a89ec9090f32cc44b0826816ba1_60.png)

Great， now you know how to build up strings from smaller pieces。



![](img/392e4a89ec9090f32cc44b0826816ba1_62.png)