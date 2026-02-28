# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P19：18_模块2 3 1 常量.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/c3efb584d684698414429a0431b2882e_1.png)

🎼う。🎼Yeah。So let's talk a little bit about a constant。

 so constant is pretty obvious what a constant is， it's an expression whose value is known at compile time right so you know it and it never changes。

So you can just basically declare a variable to be a certain value and it holds that value for all the time as long as the program is running。

The type is inferred from the right hand side of the assignment so for instance here we've got we say constant x equals 1。

3 so that's going to set x to the value 1。3 and the compiler looks at 1。

3 sees that that's a floating point and so X becomes a floating point so it infers from the right hand side of of the assignment what the type of the variable needs to be and it is held constant can't be changed you can assign many at once so constant we know y equals 4 z equals high right you can give a long list if you want to。

So that's what a constant is。Now Iiota is a function used to generate constants。

It's sort of interesting。 So it generates a set of related but distinct constants。

 So when do you use this， use this when you have to represent some property or some some property that has several different distinct possible values。

 So this is also known as one hot。 So if you know there's a basically if you have a variable。

 And you know， it's going to be one hot coded， right， This variable can have one of five values。

 let's say。And so you want each one of these five values to have to be a distinct constant right now in a situation like this and just examples of such things。

 days of the week right you got seven days of the week and you want each day of the week if you want to define a constant for each day of the week。

 Monday， Tuesday， Wednesday， you want them all to be constants which are different。

 but which are different you don't particularly care what the value of the constant is as long as Monday is different from Tuesday。

 which is different from Wednesday， months of the year is the same thing right so key thing about these constants is when you use Iiota to generate these constants。

The constants need to be different， but the actual value of the constants is not important。

 so if I have Monday， Tuesday， Wednesday。As my constants。

 I don't care if Monday is 500 or 5000 or2 or something as long as Monday is not the same as Tuesday。

 which is not the same as Wednesday right so that's the case where you can use Iiota。

 if that's the case you need to represent some set of constants with all different values。

 you don't care exactly what the value is， but as long as they are distinct constants。

 then you can use Iiota。And this is essentially just like an enumerated type in other languages。

 like in C or something like that， is the same idea。

So they give you a nice little shorthand for defining these set of constants。

So here's a an little example of how you might define something using Iiota。

 say I want to define some grades， so I make a type called grades。

 I make an in I want to represent my。My grades is integers， and I want to have these five grades， A。

 B，C， D， and F。And I know that I want ABC， DNF to be all different grades。

 so they should be represented by different integers。

 but I don't particularly care what integers they're represented by。

 I just want A to be something different than B and C and DNF。So I declare the constants， A， B，C， D。

 and F， and the first one， I say A， give the type grades， which is actually an int， St alias for ant。

A grades equals iota。 I say that on the first constant definition。 Then for B C， D and F。

 I don't have to repeat that， right， as you can see， I just say B C， D and F， I don't give the type。

 I don't say Iiota another that They just do it on the top。 And what will happen is automatically。

 Iiota will assign a value to the first constant。 And then it'll assign a different one to the next one。

 a different one to the next and so on。 And actually what it does what the implementation does is that it assign it starts at one。

 So A would be one。 B would be 2。 C would be 3， but you should not depend on that right that's not so you don't know the idea behind using Iiota is that you don't care what the actual values of the constants are。

 you just want the constant values to be different from one another。

 So it happens that the current implementation starts off at one in increments。

 but you can't guarantee that in the future， maybe that's going be changed。

 all you know about Iiota is that they are gonna be different。



![](img/c3efb584d684698414429a0431b2882e_3.png)