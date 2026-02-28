# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p26 26_03_04_typedef的用途.zh_en -BV1Kp42117vh_p26-

![](img/fffa1fe7313dc0aa6e487fd008c18168_0.png)

Here we have a struct declaration for a rectangle。 When you declare a struct， the struct tag。

 In this case， rect tag identifies the str type， but by itself is not a type name。

 When you want to name the struct type。 You have to include the struct keyword like you see here。

 Many programmers find it tedious to writestruct everywhere。 They need to use their struct type。

 So they use type def to define a new type name for the struct type。

 One way to use type def with our rectangle struct is shown here。

 The type def keyword says that we are going to make a new name for an existing type。



![](img/fffa1fe7313dc0aa6e487fd008c18168_2.png)

The new name in this case， Ret T comes last in the declaration。

 and the name of the existing type comes between them。 Notice that here。

 the existing type is struck Ret tag。 Now， we can just use rect T as a type name。

 It is an alias or another name forstruct rect tag。

 There are a couple other ways we can do the same thing with type def。

 We mention them all so that if you see one of the other ways in someone else's code。

 you will not be confused。We can combine the strict declaration and typey de into one statement。

 This follows the same rules we just discussed。The new name Reed T goes at the end of the typey de statement。

 and the existing type goes between the new name and the type f keyword。

It just happens that here the existing type gets declared in the type of statement。

The third option is the same as the previous one， except that the struct tag is omitted。

 This makes a struct with no tag and immediately aliases this struct to rec T。

Type F has uses beyond juststructs。 Sometimes we are writing some code that deals with RGB values for pixels。

 In this hypothetical example， we initially use unsigned ints to represent the red。

 green or blue components of each pixel。But what happens if later。

 we realized that it would be better to use an unsigned char since RGB values can only be between 0 and 255。

 and we don't want to waste memory？With the way we wrote the code。

 we have to go find every single place that we used unsigned int to represent an RGB value and change it。

 We can't even use the search and replace functionality of our editor。

 since there may be other uses of unsigned int that do not represent RGB values。

 so we don't want to change them。Such a change is tedious and error prone。 In fact。

 one important rule of programming is to write codes so that if you have to change something。

 you only have to change it in one place。Now suppose we had originally written our code this way。

Here we use TyefF to make RGBT an alias for unsigned int and then used RGBT as the type name everywhere we needed to talk about an RGB value with this code。

 if we want to change the type we use for RGB values。

 we can just change the type de statement and everything else will change correctly as a side benefit。

 this helps the readability of our code。 anyone reading the code can tell when a variable parameter or return value is an RGB value Since its type is RGBT。

Type De can be great to make your code easier to modify and easier to read。

