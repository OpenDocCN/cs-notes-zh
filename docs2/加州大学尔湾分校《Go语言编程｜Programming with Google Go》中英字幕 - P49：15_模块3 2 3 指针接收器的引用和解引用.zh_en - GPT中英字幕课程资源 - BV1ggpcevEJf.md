# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P49：15_模块3 2 3 指针接收器的引用和解引用.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 3， object orientation and go， topic 2。3 point receivers referencing and dereencing。



![](img/ad6586b9e7b731ef4510a2c154a3ac8f_1.png)

So one thing about using a pointer receiver is that there's no need to dereference the pointer inside the method。

 So what I mean by this is that okay so let's take a look at this example offset X。

I want it to have a pointer receiver because I want offset X to actually be able to modify the X coordinate of the type。

 so I have to pass it a pointer to P。 So now if you look to the left of the function name offset X。

 you see P star point right so the receiver is a pointer type。Now， notice inside the function。

 I say p dot x equals pt x plus V。I don't say。Star P do x equals star p x plus V right That's a dereencing that you would normally use with pointers。

 I don't have to do that because this is a common enough thing that Go just allows you to get basically the compiler recognizes it。

 It says okay， I know what you mean but you can just say P dot X and it knows even though it' a pointer it knows to get the X It knows to basically dereence it automatically。

 So it's just a handy shorthand。 You don't have to do the dereencing when you're doing this。

And likewise， there's no need to reference either。 So， so say I'm in my main and I want to。



![](img/ad6586b9e7b731ef4510a2c154a3ac8f_3.png)

I've defined my offset X as I showed you where it accepts a pointer to sorry the receiver type is a pointer right now in this case in this main。

 I'm declaring this P， this point P， I'm making it 0。

3 comma 4 So P is actually a struct right it is the type。 It is the actual struct。

 it is not a point to de struct， it is de struct。But then when I call offset X。

 I say P offset x when really offset x is supposed to have a pointer receiver。

 you would think you would have to say a percent p do offset x， but you don't。

 you can just say p offset x and the go compilepir recognizes that just because this is a common thing to do。

 So it just makes it easier to convenience。 So when using pointer receivers。

 it is good programming practice to either have all methods use pointer receivers or have none of them use pointer receivers it's just a good standard。

 It's easy to get confused。 So if you have some methods use pointer receivers and some not use pointer receivers。

 it can get confusing， you you'll send a pointer to to the one that doesn't need a pointer and so on。

 So it's just's more appropriate to use It's a good practice。 you don't have to。

 you can makes a match you want， but it's good practice to use all pointer references for a particular type or all nonpointer references。

😊，Thank you。