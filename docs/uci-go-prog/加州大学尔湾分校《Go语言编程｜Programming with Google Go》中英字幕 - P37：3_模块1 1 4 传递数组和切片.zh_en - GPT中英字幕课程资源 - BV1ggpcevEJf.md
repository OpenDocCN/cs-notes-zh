# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P37：3_模块1 1 4 传递数组和切片.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/956ed974f3efa211775163956c332d56_0.png)

Module1 functions in organization， topic 1。4 passing arrays in slices。

So say you want to pass an array as an argument to a function。

Maybe you want to do some processing on the array or something like that inside of function。

So the arguments are all copied because this is called by value。

 so the whole array has to be copied to the parameters， and if the array is big。

 then this is a problem， it'll take a lot of time to copy， also using an excessive amount of space。

So as an example of that， we got this function foo。And it takes an argument。

 an array of three integers，3 is small， but this is just an example。

 You could imagine that could be 300，000 So it takes an array of 3 integers。

 and so that's declared their x square brackets，3 int， and it returns an integer。

And just returns the first element of the array， x braga 0。

So the function main that first defines an array， a colon equal just a three element array， 1，2，3。

And then it prints out whatever F returns， so it calls F with that array A。

 which returns the first element， which would be a 1， then it prints that out。So in this case。

 it has to copy that whole array over when it makes a function call it copies that into x。

 the parameter of fo and that waste time， you know if it's a long long array。

 so what do you do so one thing you can do about that is you can employ basically call by reference so you can instead of passing the array to fo。

 you can change fo so that it takes a point to an array。So that's what we've done here。

Function foo instead if you look at its argument' parameterist。

 it says fo and then Princes x is x star bracket 3 inch。

 so it's a pointer to a three element array of integers and then inside the function fo all it does is it it takes star x which is pointed to the array so star x is actually the array right and it looks at the zero element and adds one to it。

So it increments， it should increment the zeroth element。Then if I look at the main。

 it defines the array A， then when it calls F， it doesn't pass it A， it passes it am percent A。

 passingly pointed to A。And then it just prints out A。

 and what should happen is since F got the pointer to A， it can actually modify that array A。

And it should modify it by incrementing the first value， so if the array starts out it as  one，2，3。

 it should increment that  one， so it's 2，2，3， and then it prints the array when it prints it。

 it prints out 2，2，3。So you could do this。You could explicitly。

 you could dereference use referencing and dereferencing operations to pass array pointers and use array pointers。

 But that's messy， and it's not necessary in go lengths。

 This isn't the way the neat way to do it and go。 So the way you do it and go is you use slices instead。

 In fact， in general and go， get used to using slices instead of arrays just in general。

 So a slice is like a window on an array， right， But remember that when you declare a slice。

 if you declare a slice from scratch or make it or however you make it。

 it'll make the backing array behind it， right， So you can almost always use a slice instead of an array。

😊。

![](img/956ed974f3efa211775163956c332d56_2.png)

So passing a slice copies the pointer。When you pass an array， it copies the whole array。

 but a slice is not actually an array， it's actually it's really a structure that contains three things appointed to the array or pointed to the start of the slice in the array。

And the length and the capacity。 Okay so it is really a structure with those three pieces of data。

 one of which is a pointer。 Okay so when you so it's still the goal going is still called by value。

 But when you pass a slice since the slice contains the pointer， you're copying the pointer。

 So the called function actually， when you pass a slice actually gets the pointer。

 and also the length in the capacity。 So it can use that pointer directly and modify the slice without having you without you having to explicitly dereence and reference like we did with the array example。

 So here's an example like that here with this full function this time it takes a slice。

 I'm calling SI。 And notice that。😊，When you declare the slice， you don't have to specify the size。

 In fact， you can't specify the size。 You just give the square brackets。

 So it says SI square brackets and an int。 there's no number inside square brackets because it that means it's a slice。

 So you do that and it knows， okay， this function， fo takes a slice as a parameter。

 And then then what it does， it takes a slice and just as one to slice element 0。

Then if we look at the main this time what we do is when we declare we don't declare an array。

 we declare a slice and it's only slightly different。 So this time when we declare a。

 make that array or rather not a not array， it is a slice now a colon equals square brackets and1，2。

3 the only difference is I didn't specify a size inside the square brackets。

 I didn't put a three like I did when I declare an array this time I just put square brackets。

 So now it recognizes that a is actually a slice， So then I can just call fo past the the slice or a。

 which is now slice and it works exactly the same as the last program and so when you print a。

 it will have incremented the first element which was once an oce2。

 So it'll print out two co2 comma 3 so in general in go try to use slices instead of arrays and specifically when you want to pass an argument an array argument don't pass an array argument。

 pass a slice argument because then you don't have to do all the copy。

It's associated with with that would be associated with an array。Thank you。

