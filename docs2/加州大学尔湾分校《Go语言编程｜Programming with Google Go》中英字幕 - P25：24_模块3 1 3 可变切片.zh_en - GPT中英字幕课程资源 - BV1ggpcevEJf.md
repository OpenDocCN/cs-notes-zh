# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P25：24_模块3 1 3 可变切片.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/5acd5910a16cb2b8b09051d96a7c3d86_1.png)

🎼う。🎼Yeah。So there's a function called make that can be used to make slices。

And you can make other things with it too， but right now we're going to talk about make slices。

So the one way that we made a slice， the first way we talked about making the slice was just to make the underlying array and then make the slice after it。

Also， you can initialize the slice directly with a slice literal。 We talked about that。

 This is the third way。You make make the slice directly。

 but you're not initializing with any particular values， so this is common。

This is when it's a case like this where you don't you want to use a slice because it has this variable size ability and you don't care there's an array in the back right but you want to initialize a slice to a particular size。

 so at least at the beginning， so one thing you can do is call make there are two ways to call it you call it with two arguments at three。

😡，If you call it with two arguments， the two arguments of the make are the first argument is the type。

 so the type of the objects that are going to be inside the slice。

 so if it's a slice of ints or slice of strings or something like that。

 that would be the first argument， int string。And then the second argument is going to be the length of the slice。

 Now， when you use make to make a slice， the length is equal to the capacity because it makes the underlying array and the array is exactly the same size of the slice。

 so the length of capacity are the same。So when that is anyway when you use the two argument version of make。

 so you can see here SLI equals make， we say bracket int to tell the type and then 10。

 so since I gave two arguments it figures okay， length and capacity are the same so the underlying array is the same as same size as the slice and the slice points to the beginning starts at the beginning of the underlying array。

Now， the three argument version of make。Instead， you specify the length and the capacity separately。

 So that means that the underlying array is actually bigger than the slice。

So in this case we got SLI equals make first we give the first argument the type bracket int second argument is the length of the slice。

 the third argument is the capacity which is the size of the array。

 so in this case our slice is size 10， but the array is size 15 so we can increase this slice up to size 15 if we want to。

So there's an append function that can be used with slices and it's used to increase the size of a slice。

So if you want to add stuff onto the end of a slice and increase the size of the slice in doing so。

 you use the append function Now note that this is a key advantage right compared to regular arrays that you see in regular languages。

 you can't just add things to the end of an array and continually increase its size。

 but with a slice you can。So it adds the element， the element。

 the append adds you can add one or more elements， in this case we'll do one。

 but it adds the element to the end of the slice。😡。

And which means it inserts it into the underlying array。

 so it increases the slice up to the capacity of the underlying array and increases the size of the array if necessary。

 so if you reach the limits of the array size it'll make a new underlying array that's bigger so that you so append never has to stop appending。

 you can continually append even beyond the size of the array and it'll just increase the size of the array。

😡，You don't want to do that there's a time penalty for that， but it'll do that so as an example。

We make a slice， SLI， we call make， so it the size of the slice， the length of slice is0。

 but the length of the underlying array is3。So then then I want to put something into the slice。

 So the slice is empty right the size is0。 So I say I append the number 100 onto the slice。

 so I call a pen。 I pass the first argument， I pass the slice the name of the slice and the second argument is 100。

 The number that I want to put into the slice。 So it puts it in in order to add that on it has to increase the length of the slice。

 So now the slice's length would be increased to accommodate the new number that it put in there。

 So that's how you would use a pen in general。

![](img/5acd5910a16cb2b8b09051d96a7c3d86_3.png)