# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p92 26_03_05_ArrayList用于唯一单词.zh_en -BV18U411U729_p92-

![](img/6f8c46db361b2d6676416ac5d5af9ac8_0.png)

Hi， we're going to show an example of how the array list structure works。

 We'll show code that keeps track of how many times each word in a file occurs。 The file。

 or it could be a URL， could be a large file like text from Shakespeare's Romeo and Juliet。

 or like the sayings of Confucius。We don't know how many different words there are before we start reading the file。

 so we can't easily use an array。Instead， we'll use two array list structures。

 one that holds strings and one that holds integer values。 We'll need integer instead of int。

 We'll explain why。

![](img/6f8c46db361b2d6676416ac5d5af9ac8_2.png)

The case value of the array list， whose name is my freaks， will store an integer。

 The number of occurrences of the case value in the instance variable array list。 My words。

 the names are names of instance variables that we'll see in the code。 As shown here。

 we see two occurrences of the。With a string and an integer stored in the location with index 0 in the two different array lists。

Similarly， there are three occurrences of the word dog and one occurrence of the word green。

 Let's write code。 We've got a class word frequencies。

 I'm going to open it up and take a look to see how it works。

 And one way we can easily see how it works before we look at the code is simply to run it。

 So I've created。

![](img/6f8c46db361b2d6676416ac5d5af9ac8_4.png)

An instance of it on my object workbench。 And I'm going to right click and run the tester method。

I'm going to open the file Romeo。text， the entire text of Shakespeare's Romeo and Juliet。



![](img/6f8c46db361b2d6676416ac5d5af9ac8_6.png)

And I can see that there are 5，895 unique words。 What I'd like to do with array lists is count how many times each word occurs。

 so I'll find out how many times the occurs， Montague， Capulet， all the words from Romeo and Juliet。



![](img/6f8c46db361b2d6676416ac5d5af9ac8_8.png)

Just going through this code very quickly to highlight the key features before I add the counting。

 I have an instance variable， my words。Which is initialized to be able to hold strings in the constructor。

In tester， I call the function find unique。Which creates a file resource。

 And because it had no parameters that allowed me to open up any file I wanted。

It loops over every word。Convert each word to lowercase。If the word has never been seen before。

 which I find out by using the array list method dot index of。

 which is a method whose same name we've seen in the string class。 If it has never been seen。

 I add it to my words。 Now， what I want to do is have a parallel array。

 I will call it my freaks for my frequencies。 So I need another instance variable。

This has to store integer values and unfortunately with array lists in Java， I must use integer。

 you've seen this before with integer do parsant similar to the class double do parse double。

 I'll explain this as I go。 I need to store integers。 I'm going to create place for it。

 I'm going to initialize that in the constructor to a new array list of integer values。



![](img/6f8c46db361b2d6676416ac5d5af9ac8_10.png)

And then if I've never seen the word before， that means this is the first occurrence。

 so I'm going to add to the end of the array list， the value 1。

This is just like the idea of the first time you see a word。It's occurred once。

 but if I've seen it before， this is in my else statement。If I've seen it before。

 I know where it is because index tells me。 so what I'm going to do is find the value that's in my freaks。

 This is the number of times that's already occurred。I can get this value。Using the get method。

 And then I can set the value。In my freaks。To value plus one。

So let me make clear what I've just done there。 I've accessed the value at the location specified by index。

 which was returned to me by the dot index of method。

 And the idea here is that if the word the occurs in location 500 of my words。

The frequency or number of times that occurs is in location 500 of my freaks， they match up exactly。

This will， I hope， compile。Cannot find my freaks。So I've looked up here and I can see my freaks。

 my freaks。My freaks， that's because I forgot to say set the name of the method to set the value is set。

Now I'm ready to run it。But I haven't printed any values after I've printed them。

 So after I've tested them all and found them， I will literally print every single word and how many times it occurs。

 So I'm going to use the standard for loop that loops over array values or array list values。

Size is the method that tells me how many there are。And I'm going to print。The number of occurrences。

 which is in my freaks。A tab character。 And then the word itself。



![](img/6f8c46db361b2d6676416ac5d5af9ac8_12.png)

That compiled， I'll create a new one by right clicking。And creating a new object。

And then I'm going to run the tester method on this object。By right clicking。

There's the right click run Tester。Let's count Romeo。



![](img/6f8c46db361b2d6676416ac5d5af9ac8_14.png)

And you can see how many times different words have occurred in Romeo。 For example。

 the has occurred 677 times Romeo 48 and Juliet 23。

 Another word that occurs often is Juliet with a period。

 I haven't taken into account punctuation at all and from occurs 86 times。

 Let's make sure that part of the code is clear。

![](img/6f8c46db361b2d6676416ac5d5af9ac8_16.png)

![](img/6f8c46db361b2d6676416ac5d5af9ac8_17.png)

I've。Accessed the value in my freaks and stored it in the int value。

 And then I've set the value at index to value plus 1。

 because array lists use integer rather than int。 This is a two step process。

 Find the value and then store the value。 That's what we need to do with integer。

 which would be a little bit different than we had with int。 We'll see that in a later video。

 Let's look down here。 My freaks do get K。Returns the case value of the frequency array list。

 and my words。ge k returns the corresponding word， the 23rd frequency is the number of times the 23rd word has occurred。

Now that you know a little more about a Ray list， let's write some code。

