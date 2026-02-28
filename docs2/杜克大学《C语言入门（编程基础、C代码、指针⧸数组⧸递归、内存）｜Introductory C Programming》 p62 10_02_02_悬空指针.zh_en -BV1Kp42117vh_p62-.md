# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p62 10_02_02_悬空指针.zh_en -BV1Kp42117vh_p62-

![](img/fa880ba1018c4ddef089030dff2fb4ba_0.png)

In this video， we're going to look at executing some broken code that results in and uses a dangling pointer。

 The first thing that main does is declare an int star P and initialize it with the return value of in knit array of2。

 we make a box for P。 create a frame for inni array Pass the argument to for how large and move our execution arrow into the function。

 The next thing that happens is we declare my array of size 2。

 So we get space for two ints in this frame。 Note that these boxes are not to scale。

 How large would take up the same amount of memory as each element of my array。

 Each box would take up four bytes。 If the size of an int or4 bys。😊，We enter the for loop。

 and I has the value 0。 We initialize the0 with element of the array to 0。

 Then go through the loop again， where I has the value 1。

 and we initialize my array at one to have the value 1。 The The array is fully initialized。

 and we have finished our for loop。 Now， we've reached the line。 Re my array。

If you wrote this broken code， you were probably hoping it would copy the array back into。

 for example， Main's stack frame， however， that won't work for a variety of reasons。In mainine。

 we've only asked for space to hold a pointer to an int and not some array of arbitrary size。

 If we wanted an array in main's frame， we would have had to declare an array there and specify its size。

 We will see later in the specialization how we can allocate memory outside of the stack。

 which would persist across function calls。 But we haven't learned how to do that yet。

 So when we return my array， the value of the expression My array is a pointer to the first element of the array。

 So the return value that we return to call site location 1 is just a pointer to this location。😊。

So when we return， P is going to be assigned this pointer。

 However in the process of returning from this function， that frame goes away。

 So now this pointer points over here where nothing really exists anymore。

 We still assign that value to P。 and P points right there in memory at whatever happens to be there。

 But there's no box associated with that anymore。 It doesn't belong to a particular variable。

If nothing has changed that memory location， it will still hold 0。

 but because that memory location could be reused for something else， it could change unexpectedly。

 So at this point， p is dangling。 noticeice how it's pointing at nothing in our diagram。

 Dereferencing P is therefore erroneous behavior。 So if we were to go inside this for loop。

 and try to print p at 0， it would be whatever value is in memory where p is pointing。

 that may still be 0， or it may not be。 We don't really know what we're going to get。

 If I run this on my computer I get 0。 and then 0 again for the second iteration。The first time。

 presumably it gets zero leftover from my array。But when it calls printf。

 printf's frame goes right here， overr this space。 So it's going to destroy the value1 that was in the box previously here。

 and this is going to read some value that happened to be in printf's frame from the previous call。

 regardless of what happens。 This code is broken， and we shouldn't write code like it。



![](img/fa880ba1018c4ddef089030dff2fb4ba_2.png)