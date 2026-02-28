# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P24：23_模块3 1 2 切片.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/fed1f61796b725bd38c09c114a4422b5_1.png)

🎼う。🎼Yeah。So a slice is a data type that you don't see in a lot of other languages。

 a slice is a really useful data type。 So a lot of times actually slices are used instead of arrays because they're flexible。

 you can change their size you can increase them in size。

 So let's talk about slices and how they define。 Basically a slice is a window on an underlying array。

 So for every slice there's got to be some underlying array。 that is the basis for the slice。

 The slice is just a window of it， a piece of it。 So you've got a long array of 100 elements。

 the slice is just maybe it's just 3，4 and 5 or something like that elements or 5，6，7，8。

9 something like that。 that's basically what a slice is。

 a window on a larger possibly larger array doesn't have to be larger。

 The array can be the same size of the slice right then the slice is just。😊。

Looking at the entire array， but the array can be much bigger than the slice and the slice can be just a smaller window on it。

 So that's essentially what a slice is。So slices have they can have variable size up to the size of the array。

 This is one thing that's really nice about slices。

 you can increase the size of a slice See an array is a fixed size thing。😊。

So let's say I have an array of size 100 and I have a slice of size 10 which on that array and it's the first 10。

 I can increase the size of the slice to 20 and just look at the next 10 elements of the array and then I increase it to 30 and include the next 10 elements of the array so slices you can increase the size of the slice where you can't do that to an array。

😡，So that's a good feature of slices。Now， every slice has basically three properties。

One is the pointer。 okay that indicates the start of the slice。 So every slice。

 since it's a window on an array， it has to point to some element of the array that is the first element that is included in the slice。

 That's the pointer。The next thing in a slice， next property of a slice is its length。

 it's the number of elements in the slice。Because they all have a length。 The third is the capacity。

 So the capacity is the maximum number of elements in the slice。 Now。

 that's defined by looking at the pointer， which is the beginning of the slice and looking at the difference between that and the and the distance to the end of the whole array。

 because a slice its size can be increased up to the size of the hole up to the end of the array。 So。

 for instance， say you got an array of size 100。 You got a slice of size 10。

 You can increase that slice of size， say the slice starts right the beginning of the array。

 You can increase the slice of size all the way to 100。 if you want to。 So it has a capacity of 100。

 But say you got an array of size 100。 But this slice starts at array index 10。

 Then it can only be increased to size 90， because by then you reach the end of the array。

 So the capacity of that slice is smaller。 So let's look at an example to see what I mean by these things。

😊，Sllic example。 So first we start with the underlying array， we've got this array。

 we define it with this literal， it's got this A， B，C， D， E， F， and G， that's the array。

Our array of strengths。Now， then we define two slices on this with that array as the underlying array。

 S1 and S2。Now， here's how we define these slices。 We say we use this bracket notation and we use the colons inside the brackets to define the beginning and the end of the slice。

 So if you look at S1， S1 colon equals array A R R bracket 1 colon 3。

 The one is the pointed to the first element of the array that is inside the slice and the three is the index just after the end of the slice。

 So that slice S1， it includes array elements1 and 2 not3。

 So the second number after the colon is just after the end。 Now if we look at S 2。

 that's2 colon 5 right So S2 start to 2 include3 and 4 does not include5。

 So we can see this in we can see the picture down here at the bottom。😊，He got the array in blue。

 the whole array， and it has the ABCD EFG。Then in red， I've highlighted S1 and S2， so S1。

 it includes index1 and 2。RightBecause one column three， so three is just past one past the n。

 and as two includes two， three， and four。And notice that these two slices overlap and that's okay。

 if you look at S1 and S2， they both include array index 2 so and that's fine slices can overlap and refer to the same elements inside the underlying array。

All right， so the length and capacity。So there are two functions linen cap which return the length and capacity of a slice。

 So we got our array a1 here and it's three elements long AVC。

 Then we define a slice Si1 I'm calling it this time。

 and that is the array0 colon 1 so that means that this slice includes array index 0。

 but not array indexd 1 So it just its length is actually1 should be one right it only has one element in it。

 array index 0。But so if we now in the next statement we' do the print name。

 we print the length and the capacity， the length is one0 and then0 is the only thing that's actually in the slice。

 but its capacity is still three because because it could be its size could increase up to three if why increase the size of the slice to go all the way to the end of the array since the array has three elements in it and we're starting the slice at the beginning at array index0。

 we could go all the way through it it 0，1 and 2 and the length of the slice could be up to three so its capacity is3。

Now accessing slices or really referring to slices。So when you write a to an element in a slice。

 you are writing to the underlying array。And overlapping slices can refer to the same array elements。

 so you change one slice。 you can change the underlying array and you can change any other slice that also accesses that it also includes that array element。

 So here we got these in this picture， we' shown this array。

 we got S1 and S2 or two different slices defined on it。

 Now see in green circled that array element2 with a letter the string C in it right。

So that one is actually included in S1 and in S2。Now， in S1 with respect to S1。

 that is the S1 bracket1， it refers to that second element of the array right because S10 would refer to the first element of the array because that's S1 starts。

 So S1 bracket 1 refers to that C， that letter C。Now S2 second element to the array is the first element in S2。

 so that's the same as S2 bracket 0， so these two print statements will print the same thing。

 the letter C， because S1 bracket1 is the same as S2 bracket 0 they're both referring to the same element in the underlying array。

Now， we talked about array literals。 You can also have slice literals。

 They can be used to initialize a slice， just like an array literal can be used to initialize an array。

 Now， remember that every slice has to have an underlying array。 So when you initialize a slice。

 that means you're creating an array。 you have to create the underlying array。

 and the slice just it covers the entire array。 So when when you use a slice literal to define a slice。

 it actually creates an underlying array and it creates a slice to reference the entire array。

 So the length and the capacity of the slice are the same So the slice。

 if you do this if you use a slice literal to create this array。

 the slice will its pointer will points to the beginning of the array and its length will be the length of the array and its capacity will also be the length of the array。

 So the slice points to the entire array when you use a slice literal to define in this way。

 So we can see that here。😊，We define using a slice literal。

 SLI is defined as a slice literal and it defines the underlying array and you know that this is a slice literal because you can see where I say SLI colon equals brackets。

 normally in the bracket you'd put the length if it was an array or put five or three in this case。

 or you'd put at least dot dot dot to say this is an array。

 its length should be inferred from the number of elements inside the curly brackets。

But in this case， we didn't put anything in the brackets。 so the compiler says， oh。

 this must be a slice and what it does is it creates the underlying array and then it makes a slice point to the whole array。



![](img/fed1f61796b725bd38c09c114a4422b5_3.png)