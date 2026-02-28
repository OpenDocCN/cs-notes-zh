# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p140 20_03_02_Comparable接口.zh_en -BV18U411U729_p140-

![](img/77a693610d36b2136612c3e12bb914a8_0.png)

Now that you have seen the compare to method in quake entry。

 it is time to learn about the comparable interface， which promises this method。

 classes which implement comparable have a natural ordering。 There is some way to put them in order。

 which inherently makes sense。 The compare to method。

 which this interface promises defines this ordering。You can see the interface definition here。

 It is a bit different than what you have seen before because of the angle brackets T。

The angle brackets T at the top specifies a type parameter for this interface in this case it specifies what type can be compared against Quake entry implements comparable of quake entry。

 meaning that you can compare one quake entry to another。

That type parameter can be used in the rest of the interface definition and will be whatever type is passed as a parameter。

In the case of comparable of qua entry， the Compare to method would take a quake entry object as its parameter。

So why does comparable have the angle brackets T while it's not just used for quake entriesries。

 In fact， comparable is a built in part of Java and Quakeent is not when Java was created。

 its authors were not thinking about quake entriesries。

 but instead making something generic enough to use with any totally ordered type。

There are many types that implement comparable， including several that you have seen before。

 strings can be compared to strings， integers to integers， and so on。



![](img/77a693610d36b2136612c3e12bb914a8_2.png)

Let's take a minute to look at strings since their natural ordering is easy to understand。

 The string class implements comparable of string。 You can compare any two strings to put them in order。

 What ordering is natural for strings。 Albetical order。 If you were to alphabetize things。

 Apple would come before bear。 So Apple is less than bare， which is less than cards。

 which is less than dno。 As you may remember， strings can hold any character， not just letters。

 So how do you alphabetize such strings， and what happens if they contain the same letter。

 but in different cases。 strings do compare two method takes care of all of these。

 The ordering it uses is technically called lexical graphical ordering。

That's a fancy way of saying that you look at each letter from start to end as long as they are the same。

 you keep going when you find a difference， that tells you how to order things。

 This is what alphabetical ordering does for letters。

 It is just the technical term for the more generalized algorithm for any characters。For example。

 if you wanted to compare what exclamation mark to what question mark you would look at the capital W's see that they are the same。

 the H's， A's and T's are the same but then the exclamation mark is different from the question mark you then order these two strings based on which is greater or smaller exclamation mark or question mark does that even make sense well remember everything as a number Java can just compare the two characters for you and will do that comparison based on their numerical value should you remember the numerical values of these characters。

 of course not you generally don't need it and if you ever do you can look it up or write a small test program just like we did。

To compare capital what with lowercase what， Java would find a difference in the first character。

 it turns out that capital letters have lower numerical values than lowercase letters。

 so capital what is less。Comparing these last two strings proceeds much like comparing the first two。

So how does compare to return less than equal to or greater than？It returns an integer。

 which is negative for less than。 For example， Apple dot compared to bear returns negative1。

 If they are equal， it returns0， such as when comparing bear to bear。 Finally。

 it returns a positive number for greater than Dno dot compared to cards， returns positive one。

Note that you should not rely on specific negative or positive values like negative or positive1。

 the method only promises to return a negative or positive number， for example。

 comparing Apple to Dno gives negative3 and comparing lowercase what to uppercase what gives 32。



![](img/77a693610d36b2136612c3e12bb914a8_4.png)

These may seem weird， but actually make a lot of sense。

 Often compared to is implemented using subtraction， as is the case in string。

 When it finds a difference in the characters， it subtracts them from each other and returns the result。

 This is yet another instance of the everything is a number principle in action。

